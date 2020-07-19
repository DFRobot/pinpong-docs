PinPong类 PinPong class
========================

--------------------
构造器 constructor 
--------------------

创建和初始化一块板子。

board = PinPong(boardname,port)

- boardname: 板子的类型，目前支持“UNO”和“LEONARDO”

- port: 设置对应的端口号，如省略参数则自动识别选择一个端口。如何查询端口号，见安装及快速开始教程。

----------------
方法 method
----------------
::

    board.connect() 

    连接arduino板，检测固件版本，若没有烧录固件或版本有误，会烧录最新固件。



