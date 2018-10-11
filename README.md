# WeChat Bomb

微信轰炸

10行python代码实现微信轰炸

### 说明

- 站在巨人的肩膀上
- 基于python，这个小程序是用python写的
- 使用的是python第三方库itchat，itchat模块是一位叫`littlecodersh`的大神写的模块，附上大神的github地址https://github.com/littlecodersh/ItChat，有兴趣的朋友可以去尝试玩一下itchat模块，很有趣的！！！

### 准备

- Python3.6 需要安装python3.6并配置好环境路径

- 安装好python后，打开电脑的CMD终端输入`pip install itchat`安装itchat模块

- 需要设置好默认看图软件

  <!--登录微信的时候需要扫码，如果没有设置会报错-->

### 核心代码
```python
import itchat
import time

print('扫一下弹出来的二维码')
itchat.auto_login(hotReload=True)
boom_remark_name = input('输入你要轰炸的人的微信备注，按回车建继续')
message = input('输入你要轰炸的内容，按回车键开始轰炸')
boom_obj = itchat.search_friends(remarkName=boom_remark_name)[0]['UserName']
while True:
    time.sleep(0.5)
    print('正在轰炸。。。')
    itchat.send_msg(msg=message, toUserName=boom_obj)

```
### 代码讲解

`import itchat`

导入itchat模块



`import time`

导入time模块



`itchat.auto_login(hotReload=True)`

登录微信，采用热加载的方式登录网页版的微信，会生成一个itchat.pkl的文件，用于保持登录状态，有点类似于cookie



`boom_remark_name = input('输入你要轰炸的人的微信备注，按回车建继续')`
这里一定要输入你给微信好友的`备注名`，否者无法定位到好友



`message = input('输入你要轰炸的内容，按回车键开始轰炸')`

这里输入要轰炸的内容



`boom_obj = itchat.search_friends(remarkName=boom_remarkname)[0]['UserName']`

这里通过微信好友的`备注名`找到微信好友的信息，再通过`UserName`定位到好友



`while True:` 死循环轰炸
	`time.sleep(0.5)`设置睡眠，以免出现消息发送频繁导致不能发送微信消息，此处可自行设置，睡眠时间不能太短
	`print('正在轰炸。。。')`
	`itchat.send_msg(msg=message, toUserName=boom_obj)`


### 如何使用

- 打开CMD终端

- 输入python
- 将wechat_bomb.py文件拖入终端
- 按回车

- 扫一下弹出来的二维码，确认登录微信

- 输入你要轰炸的人的微信备注(!!!一定要是微信好友的备注，没有备注请添加备注)

- 输入要轰炸的内容

- 按回车键开始轰炸

### 如何退出

按Ctrl + C 退出轰炸

### 为什么要写这个程序

本人有一位发小好赌，因为赌钱输了好多钱，也欠了好多钱，他向身边的人借了好多钱，也包括我。

出于朋友的关心，我前前后后借给他有四五万，他也陆陆续续的还钱给我了，但还了两万多之后给我就一直联系不上他，甚至把我的QQ拉黑，更令人生气的是他甚至换了电话，使我无法联系到他，但令人庆幸的是他并没有将我的微信拉黑，只是我给他发微信催他还钱他不回我信息。

由于他一直不还钱给我，也给我带来了一定的烦恼，所以我产生了一个很可怕的想法，那就是轰炸他的微信，让他还钱，于是我开始接触了python的第三方库itchat并且迅速的写出了微信轰炸的小程序

令人意外的是我轰炸他之后，他就给我回微信信息了，并且把剩下的钱还给我了，从轰炸到他还钱给我，用了不到五分钟的时间，我有点小开心，因为他把剩下的钱还给我了。但我也有点愧疚，用这种手段让发小还钱。

### 别太贪玩哦

一直轰炸朋友会让朋友将你拉黑

