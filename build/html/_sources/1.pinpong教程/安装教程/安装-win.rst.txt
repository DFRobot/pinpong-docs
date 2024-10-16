
==================
Windows平台安装
==================

1. 安装Python3。pinpong库依赖Python，因此请确保电脑安装了Python3，如果已经安装，此步可以略过。 
 
- 如果没有安装Python3，则需要进行安装, Python下载地址： `点击打开 <https://www.python.org/>`_ 

.. image::  images/win_installpython1.jpg

- Windows平台对应点击Windows，然后选择最新版本下载（也可选择其他版本）

.. image::  images/win_installpython2.jpg

.. image::  images/win_installpython3.png

- 下载完成后根据引导进行安装，注意安装最后一步勾选add to path，将python加入到环境变量。
    
.. image::  images/addpath.png

2. 打开命令提示窗。win+R快捷键，输入cmd

.. image::  images/win_install1.jpg

3. 安装pinpong库。小黑窗中输入pip install pinpong ，等待片刻即可安装完成。

.. 注意:: 如果网络较慢安装不成功，可以指定国内源进行安装： pip install pinpong -i http://mirrors.aliyun.com/pypi/simple/

.. image::  images/win_install3.jpg

4. 帮助命令。在小黑窗中输入pinpong ，即可输出当前版本信息、官方文档网址、库列表查看、端口号。

.. image::  images/pinpong-cmd-win.png

开始第一个程序
-----------------

#. 连接arudino uno板至电脑；
#. 打开IDLE编辑器，新建文件(New File)；
#. 从本文档“PINPONG示例”复制“blink”示例程序的代码到IDLE中，点击“运行(RUN) > Run Module”或按键盘上F5键即可运行代码；
#. Python Shell窗口即会显示PinPong的logo和运行状况，Uno板载LED开始闪烁，运行成功，按键盘上的Ctrl+C组合键即可停止代码运行。
#. 接下来请查看其他教程或运行其他示例程序进一步学习吧。

.. image::  images/idle1.png
.. image::  images/idle2.png


