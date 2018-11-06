### Python发送邮件的能力

> 在Python发送邮件需要用到```smtplib```和```email```两个库，这两个库都是Python自带的。

#### 导入库

```
import smtplib
from email.mime.text import MIMEText
from email.header import Header
```

#### 初始化一个SMTP实例

```
stmpObj = smtplib.STMP()
```

#### 方法

|  名称  |  描述  |  参数  |
|----|----|----|
|  connect(host='localhost', port=0)  |  连接到给定端口上的主机。默认设置是连接到标准SMTP端口(25)的本地主机。如果主机名以冒号(':')结尾，后面跟着一个数字，那么该后缀将被去掉，该数字将被解释为要使用的端口号。如果在实例化过程中指定了主机，构造函数将自动调用此方法。返回服务器在连接响应中发送的响应代码和消息的二元组。  |    |
|  login(user, password, *, initial_response_ok=True)  |  登录需要身份验证的SMTP服务器。参数是要进行身份验证的用户名和密码。如果此会话中没有先前的EHLO或HELO命令，此方法将首先尝试ESMTP EHLO。如果验证成功，此方法将正常返回，或者可能引发以下异常: SMTPHeloError，SMTPAuthenticationError，SMTPNotSupportedError，SMTPException。 |    |
|  sendmaile(from_addr, to_addrs, msg, mail_options=(), rcpt_options=())  |   发送邮件。所需的参数是RFC 822 from-address字符串、RFC 822 to-address字符串列表(一个空字符串将被视为具有1个地址的列表)和消息字符串。调用者可以将邮件中使用的ESMTP选项(如8bitmime)列表作为mail_options传递给调用者。应该与所有RCPT命令一起使用的ESMTP选项(如DSN命令)可以作为rcpt_options传递。(如果需要对不同的收件人使用不同的ESMTP选项，则必须使用低级方法，如mail()、rcpt()和data()来发送消息。) |    |
|  set_debuglevel()  |  设置调试输出级别。级别的值为1或True将导致连接的调试消息以及发送到服务器并从服务器接收的所有消息。级别值为2会导致这些消息被加盖时间戳。  |    |
|  docomd(cmd, args='')  |  向服务器发送一个命令cmd。可选参数args简单地连接到命令，用空格隔开。这将返回一个由数字响应代码和实际响应行组成的二元组(多行响应被连接到一个长行中)。在正常操作中，不应该显式调用此方法。它用于实现其他方法，对于测试私有扩展可能有用。如果在等待应答时丢失了到服务器的连接，那么SMTPServerDisconnected将会被唤醒。  |    |
|  helo(name='')  |  使用HELO向SMTP服务器标识自己。hostname参数默认为本地主机的完全限定域名。服务器返回的消息存储为对象的helo_resp属性。在正常操作中，不应该显式调用此方法。必要时，sendmail()会隐式调用它。  |    |
|  verify(address)  |  使用SMTP VRFY检查此服务器上地址的有效性。如果用户地址有效，返回一个元组，该元组由代码250和完整的RFC 822地址(包括人名)组成。否则返回一个SMTP错误代码为400或更大的错误字符串。  |    |
|  send_message(msg, from_addr=None, to_addrs=None, mail_options=(), rcpt_options=())  |  这是一个调用sendmail()的方便方法，其消息由email.message表示。消息对象。这些参数的含义与sendmail()相同，只是msg是一个消息对象。  |    |
|  quit()  |  终止SMTP会话并关闭连接。返回SMTP退出命令的结果。还支持标准SMTP/ESMTP命令对应的低级方法HELP、RSET、NOOP、邮件、RCPT和数据。通常不需要直接调用它们，  |  .  |

#### 实例

```
#!/usr/bin/python
# -*- coding: utf-8 -*-
import smtplib
from email.mime.text import MIMEText
from email.header import Header

sender = '703294267@qq.com'	# 邮件发送者
receivers = ['thebulelife@163.com'] # 邮件接收者，列表
mail_host = 'smtp.qq.com'	# 邮件发送代理主机
mail_user = '703294267@qq.com' # 邮件发送者登录帐号
mail_passwd = 'umipelffvxzebfca'	# QQ邮箱开通SMTP时的16位授权码，非登录密码

message = MIMEText('Python 邮件发送测试...', 'plain', 'utf-8')
message['From'] = Header('bluelife' ,'utf-8')
message['To'] = Header('test', 'utf-8')

subject = 'Python STMP test .';
message['Subject'] = Header(subject, 'utf-8')

try :
	smtpObj = smtplib.SMTP()
	smtpObj.set_debuglevel(1)
	smtpObj.connect(mail_host, 25)
	smtpObj.login(mail_user, mail_passwd)
	smtpObj.sendmail(sender, receivers, message.as_string())
	print('Success: 邮件发送成功')
except smtplib.SMTPException :
	print('Error: 无法发送邮件')
```

#### [参考连接：https://docs.python.org/3/library/smtplib.html](https://docs.python.org/3/library/smtplib.html 'https://docs.python.org/3/library/smtplib.html')
#### [参考连接：https://docs.python.org/3/library/email.examples.html](https://docs.python.org/3/library/email.examples.html 'https://docs.python.org/3/library/email.examples.html')
#### [参考连接：https://docs.python.org/3.5/library/email.html](https://docs.python.org/3.5/library/email.html 'https://docs.python.org/3.5/library/email.html')