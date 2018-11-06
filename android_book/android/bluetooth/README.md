#### Android使用蓝牙

##### Android 平台包含蓝牙网络堆栈支持，凭借此项支持，设备能以无线方式与其他蓝牙设备交换数据。应用框架提供了通过 Android Bluetooth API 访问蓝牙功能的途径。 这些 API 允许应用以无线方式连接到其他蓝牙设备，从而实现点到点和多点无线功能。

##### 使用 Bluetooth API，Android 应用可执行以下操作：

* 扫描其他蓝牙设备
* 查询本地蓝牙适配器的配对蓝牙设备
* 建立 RFCOMM 通道
* 通过服务发现连接到其他设备
* 与其他设备进行双向数据传输
* 管理多个连接

#### 基础知识

##### 本文将介绍如何使用 Android Bluetooth API 来完成使用蓝牙进行通信的四项主要任务：设置蓝牙、查找局部区域内的配对设备或可用设备、连接设备，以及在设备之间传输数据。

##### android.bluetooth 包中提供了所有 Bluetooth API。 下面概要列出了创建蓝牙连接所需的类和接口：

* BluetoothAdapter

> 表示本地蓝牙适配器（蓝牙无线装置）。 BluetoothAdapter 是所有蓝牙交互的入口点。 利用它可以发现其他蓝牙设备，查询绑定（配对）设备的列表，使用已知的 MAC 地址实例化 BluetoothDevice，以及创建 BluetoothServerSocket 以侦听来自其他设备的通信。

* BluetoothDevice

> 表示远程蓝牙设备。利用它可以通过 BluetoothSocket 请求与某个远程设备建立连接，或查询有关该设备的信息，例如设备的名称、地址、类和绑定状态等。

* BluetoothSocket

> 表示蓝牙套接字接口（与 TCP Socket 相似）。这是允许应用通过 InputStream 和 OutputStream 与其他蓝牙设备交换数据的连接点。

* BluetoothServerSocket

> 表示用于侦听传入请求的开放服务器套接字（类似于 TCP ServerSocket）。 要连接两台 Android 设备，其中一台设备必须使用此类开放一个服务器套接字。 当一台远程蓝牙设备向此设备发出连接请求时， BluetoothServerSocket 将会在接受连接后返回已连接的 BluetoothSocket。

* BluetoothClass

> 描述蓝牙设备的一般特征和功能。 这是一组只读属性，用于定义设备的主要和次要设备类及其服务。 不过，它不能可靠地描述设备支持的所有蓝牙配置文件和服务，而是适合作为设备类型提示。

* BluetoothProfile

> 表示蓝牙配置文件的接口。 蓝牙配置文件是适用于设备间蓝牙通信的无线接口规范。 免提配置文件便是一个示例。 如需了解有关配置文件的详细讨论，请参阅使用配置文件

* BluetoothHeadset

> 提供蓝牙耳机支持，以便与手机配合使用。 其中包括蓝牙耳机和免提（1.5 版）配置文件。

* BluetoothA2dp

> 定义高质量音频如何通过蓝牙连接和流式传输，从一台设备传输到另一台设备。“A2DP”代表高级音频分发配置文件。

* BluetoothHealth

> 表示用于控制蓝牙服务的健康设备配置文件代理。

* BluetoothHealthCallback

> 用于实现 BluetoothHealth 回调的抽象类。您必须扩展此类并实现回调方法，以接收关于应用注册状态和蓝牙通道状态变化的更新内容。

* BluetoothHealthAppConfiguration

> 表示第三方蓝牙健康应用注册的应用配置，以便与远程蓝牙健康设备通信。

* BluetoothProfile.ServiceListener

> 在 BluetoothProfile IPC 客户端连接到服务（即，运行特定配置文件的内部服务）或断开服务连接时向其发送通知的接口。

#### 蓝牙权限

##### 要在应用中使用蓝牙功能，必须声明蓝牙权限 BLUETOOTH。您需要此权限才能执行任何蓝牙通信，例如请求连接、接受连接和传输数据等。
##### 如果您希望您的应用启动设备发现或操作蓝牙设置，则还必须声明 BLUETOOTH_ADMIN 权限。 大多数应用需要此权限仅仅为了能够发现本地蓝牙设备。 除非该应用是将要应用户请求修改蓝牙设置的“超级管理员”，否则不应使用此权限所授予的其他能力。 注：如果要使用 BLUETOOTH_ADMIN 权限，则还必须拥有 BLUETOOTH 权限。

> 在Android中要使用蓝牙设备要先在```manifests/AndroidManifest.xml```文件中添加```<user-permission android.name="android.permission.BLUETOOTH">```。

```
<manifest ... >
  <uses-permission android:name="android.permission.BLUETOOTH" />
  ...
</manifest>
```

#### 设置蓝牙

##### 您需要验证设备支持蓝牙，并且如果支持确保将其启用，然后您的应用才能通过蓝牙进行通信。

##### 如果不支持蓝牙，则应正常停用任何蓝牙功能。 如果支持蓝牙但已停用此功能，则可以请求用户在不离开应用的同时启用蓝牙。 可使用 BluetoothAdapter，分两步完成此设置：


* 1:获取 BluetoothAdapter
所有蓝牙 Activity 都需要 BluetoothAdapter。 要获取 BluetoothAdapter，请调用静态 getDefaultAdapter() 方法。这将返回一个表示设备自身的蓝牙适配器（蓝牙无线装置）的 BluetoothAdapter。 整个系统有一个蓝牙适配器，并且您的应用可使用此对象与之交互。 如果 getDefaultAdapter() 返回 null，则该设备不支持蓝牙，您的操作到此为止。 例如：

```
BluetoothAdapter mBluetoothAdapter = BluetoothAdapter.getDefaultAdapter();
if (mBluetoothAdapter == null) {
    // Device does not support Bluetooth
}
```

* 2:启用蓝牙
下一步，您需要确保已启用蓝牙。调用 isEnabled() 以检查当前是否已启用蓝牙。 如果此方法返回 false，则表示蓝牙处于停用状态。要请求启用蓝牙，请使用 ACTION_REQUEST_ENABLE 操作 Intent 调用 startActivityForResult()。这将通过系统设置发出启用蓝牙的请求（无需停止您的应用）。 例如：

```
if (!mBluetoothAdapter.isEnabled()) {
    Intent enableBtIntent = new Intent(BluetoothAdapter.ACTION_REQUEST_ENABLE);
    startActivityForResult(enableBtIntent, REQUEST_ENABLE_BT);
}
```

#### 查找设备

#### 查询配对的设备


#### [参考连接：https://developer.android.google.cn/guide/topics/connectivity/bluetooth](https://developer.android.google.cn/guide/topics/connectivity/bluetooth 'https://developer.android.google.cn/guide/topics/connectivity/bluetooth'https://developer.android.google.cn/guide/topics/connectivity/bluetooth)