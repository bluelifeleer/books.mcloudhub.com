### Python面向对象编程概念

##### Python是一门面积对象的编程语言，对面向对象语言编码的过程叫做面向对象编程。
##### 面积对象编程（Object Oriented Programming，OOP）是一种设计思想，OOP把对象做为程序的基本单元，一个对象包含数据和操作数据的函数。
##### 面向对象程序设计把计算机程序视为一组对象的集合，每个对象都可以接收其他对象发过来的消息，并处理这些消息，计算机程序的执行就是一系列消息在各个对象之间传递。
##### 在Python中，所有数据类型都被视为对象，也可以自定义对象。自定义对象数据类型就是面向对象中类（class）的概念。

### 面向对象术语简介

* 类：用来描述拥有相同属性和方法的对象的集合。类定义了集合中每个对象共有的属性和方法，对象是类的实例。
* 类变量（属性）：类变量在整个实例化的对象中是公用的。类变量定义的类中且在方法之外。类变量通常不做为实例变量使用。类变量也称为属性。
* 数据成员：类变量或实例变量用于处理类及其实例对象的相关数据。
* 方法重写：如果从父类继承的方法不能满足子类的需求，就可以对其进行改写，这个过程称为方法的覆盖（Override），也称为方法的重写。
* 实例变量：定义在方法中的变量只作用于当前实例的类。
* 多态（Polymorphism）：对不同类的对象使用相同的操作。
* 封装（Encapsulation）：对外部世界隐藏对象的工作细节。
* 继承（Inheritance）：即一个派生类（derived class）继承基类（base class）的字段和方法。继承允许把一个派生类的对象做为一个基类对象对待，以普通类为基础建立专门的类对象。
* 实例化（Instance）：创建一个类的实例、类的具体对象。
* 方法：类中定义的函数。
* 对象：通过类定义的数据结构实例。对象包括两个数据成员（类变量和类实例）和方法。

### Python中类的定义

#### 语法

```
class name(object):
	i=123
	def output(self):
		return "hello word"

```

###### 在类中定义方法的形式跟函数差不多，只不过不叫函数，叫方法。类中方法的调用需要绑定到特定的实例上，而函数不需要。

#### 实例

```
class People(object):
	def name():
		print("hello word")

people = People()
people.name()
```

#### 类的构造方法

类的构造方法在类初始化时可以做一些参数设定，类的构造方法使用```__init__()```定义。如：

```
#! /usr/bin/python
# -*-coding:UTF-8-*-

class People(object):
    def __init__(self, name, age, sex):
        self.name = name
        self.age = age
        self.sex = sex
    
    def getName(self):
        print("Then people name is : %s" % self.name)

    def getAge(self):
        print("Then people age is : %d" % self.age)

    def getSex(self):
        print("Then people sex is : %s" % self.sex)

people = People("苏晓晓",28,"男")
people.getName()
people.getAge()
people.getSex()

Then people name is : 苏晓晓
Then people age is : 28
Then people sex is : 男

```

###### 一个类中只能有一个构造方法。

#### 类的私有属性

###### 使用类的一个重要的作用就是安全，在类内部的所有属性对外部都是不可访问的，一般情况要访问类的属性可以使用```.```加属性名称访问，对于有些敏感的属性就随意的可以访问，这时可以使用私有属性，让类中的属性对外部不可访问。类中定义私有属性使用```__```加属性名称定义。

```
#! /usr/bin/python
# -*-coding:UTF-8-*-

class People(object):
    def __init__(self, name, age, sex, salary):
        self.__salary = salary
        self.name = name
        self.age = age
        self.sex = sex
    
    def getName(self):
        print("Then people name is : %s" % self.name)

    def getAge(self):
        print("Then people age is : %d" % self.age)

    def getSex(self):
        print("Then people sex is : %s" % self.sex)

    def getInfo(self):
        print("Then people info is name %s age %d sex %s salary %.2f" %(self.name, self.age,self.sex,self.__salary))

people = People("苏晓晓",28,"男", 18340)
people.getName()
people.getAge()
people.getSex()
people.getInfo()

Then people name is : 苏晓晓
Then people age is : 28
Then people sex is : 男
Then people info is name 苏晓晓 age 28 sex 男 salary 18340.00
```

#### 类的私有方法

###### 有时在类中有些方法只是供类内部使用，而不需要在外部也能调用，此时可以使用私有方法。在类中定义一个私有方法使用```__```加方法名定义。

```
#! /usr/bin/python
# -*-coding:UTF-8-*-
class People(object):
	def __init(self):
		pass
	def __computed(self):
		return sum;
```

#### 类的继承

##### 在面向对象编程思想中一个重要的思想就是继承，在定义一个类时可以重现有的类继承一些属性、方法。新定义的类为子类，继承的类为父类（基类、超类）。

```
class Son(People):{

}
```

* 1：在继承中，父类的构造方法（__init__()）不会被自动调用，需要在子类的构造方法中专门调用。
* 2：在调用父类的方法时需要虽上父类的类名前缀，并带是```self```参数变量。
* 3：在Python中首先查找对应类的方法，如果在子类中找不到对应的方法，才去父类中逐个查找。
* 4：在子类中不能调用父类的私有属性、方法。

#### 类的多态

###### 当子类跟父类存在相同的方法时，子类的方法会覆盖父类的方法，在代码运行时总是会调用子类的方法，称之为多态。多态意味着即使不知道变量所引用的对象类型是什么，也能对对象进行操作，多态会根据对象（或类）的不同而表现出不同的行为。其实就是父类中的方法（私有方法除外）可以在子类中重写。

#### 类的封装

###### 封装是面向对象编程思维的一个重点，就是把许多内部实现的细节打包起来，让外部看不到，而起到化繁为简的目的，比如一个计算类，至于其中是如何计算我们并不需要详细的知道计算的细节，我们只需要知道调用哪个方法，传入哪些参数能得到什么样的结果。

#### 类的多重继承

在类中一个子类可以继承多个父类称为多重继承。

#### 获取类的信息

* type()	获取类型
* isinstance() 判断两个类是否的继承关系，能用type()判断的基本类型也可以使用isinstance()判断。
* dir()	获取类的所有属性和方法

#### 类的专有方法

|  名称  |  描述  |  备注  |
|----|----|----|
|  __str__  |    |    |
|  __repr__  |    |    |
|  __iter__  |    |    |
|  __getitem__  |    |    |
|  __getattr__  |    |    |
|  __call__  |    |  .  |