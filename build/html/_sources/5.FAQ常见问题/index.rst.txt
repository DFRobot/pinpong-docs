========
常见问题
========

虚谷号上出现错误：ImportError: cannot import name 'Pin'
-----------------------------------------------------------------

#. 尝试先重启虚谷号
#. 重启后如果依然出现，则先尝试更新pinpong库，终端运行: pip install -U pinpong
#. 如依然出现，则尝试卸载重装pinpong库,终端运行: pip uninstall pinpong  ，然后重启虚谷号后重新安装: pip install pinpong


使用pinpong库控制的硬件可以脱离电脑运行吗？
-----------------------------------------------------------------

#. pinpong是一个Python库，主要实现硬件与Python的交互，因此只有能运行Python（注意: Python和microPython_ 不一样 ）的设备才可以使用，因此如果要脱离PC，可以使用树莓派、LattePanda等便携式单板计算机。
#. 使用实时通信的方式与Python交互运行，后续将考虑开发通过网络的方式进行通信以实现在电脑上运行pinpong（Python），通过网络实时控制带网络功能的硬件设备。

..  _Python和microPython: https://www.baidu.com/s?ie=UTF-8&wd=micropython%E5%92%8Cpython


