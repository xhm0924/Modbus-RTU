# Modbus-RTU V5版本调试精灵
## 起因---向经典致敬！

1. 本人是从事嵌入式单片机开发工作，在工作中调试MODBUS时，经常使用经典的Modbus调试助手，给工作带来了便利；但是老版本的软件也有一些参数的设置不太方便，比如**地址**为8进制数据，写入**数据** 为16进制数据，**数量**为10进制数据，**端口**总是显示COM0~COM8。

2. 老版本的软件是用VC开发的，它的作者已经不更新的，预留的网站也已经打不开了。

3. 最近在新学Python，所以就花了两天时间用Python仿做了这款复古界面风格的Modbus调试精灵，同时也向经典致敬！！

## 上传到GITHUB

软件制作完成后，我在 [[阿莫电子论坛](https://www.amobbs.com/thread-5685530-1-1.html)] 分享了我的源代码和EXE文件。有坛友建议将代码托管到GitHub。我认为是可以的，虽然之前没有使用过GitHub（电子开发人员用github并不是很多），但是这是个趋势，我有一颗好学的心......

所以就有了我与github的第一次。

当然我现在我的电脑上熟悉了一下githut的操作......在push的过程中，我发现README.md文档还不是纯文本txt，这个排版也比较有趣，索性有研究了一下Markdown......自己挖的坑自己填！

## 软件说明 ##
软件是用Python3.4和PyQt5制作的，当然还使用了Pyserial库
界面没有使用Designer制作，纯手工代码摆放!~_~! (控件摆放花了大部分时间！)

![软件界面](https://github.com/hechao17/Modbus-RTU/raw/master/md_pic/face.png)  

软件主要的功能和相对老版本的变化有：

1. 支持Modbus-RTU串口通信，目前支持0x03，0x06，0x10指令。
2. 增加了端口扫描功能，自动获取端口号。
3. 修改原来的地址输入8进制，写入数据16进制，数量为10进制的问题，现在统一为10进制。
4. 修改了写多寄存器时，数据输入的一些校正。

---

软件做完后，我电脑上刚好有Pyinstaller库，就想用它来打包成EXE，这样电脑没有安装Python的人也可以使用。但是没想到过程也并不十分顺利，我的一些图片资源打包不进去，～～坑！

经过一个晚上的努力，终于搞定。不过EXE的体积好大！（这应该是Python的通病吧！）

图片资源不能打包解决的办法参考了百度：

1. 将图片先转换成py文件
2. 然后在项目中需要添加图片文件时，先将py文件还原为临时图片，项目引用后，将临时图片删除即可

![文档说明](https://github.com/hechao17/Modbus-RTU/raw/master/md_pic/file.png)  

所以大家在工程文件的png文件中，可以找到 **“png2py.py”** 文件，就是用来修改将图片png转化为py文件的工具，使用的是python自带的base64库。

在项目目录下的 **“py2png.py”** 文件则是通过py文件生成临时图片的工具。

**“pytoexe.py”** 文件则是用来打包exe文件的，注意大家打包的时候,需要修应该的里面的打包的绝对路径。

**“modbus-rtu.py”** 就是主工程文件。

----------

exe和源程序都奉献给大家，供大家参考！！
由于是业余python新手，第一版程序没有优化，github也是第一次托管程序，大家多包涵！希望大神多提意见！

如果大家能帮忙测试测试软件，那就更谢谢大家了！

----------
