掌控板示例-RGB灯控制
===========================================

.. code-block:: python

    # -*- coding: UTF-8 -*-
    #实验效果：控制掌控板板载RGB灯
    #接线：使用windows或linux电脑连接一块掌控板主控板

    import time
    from pinpong.board import Board
    from pinpong.extension.handpy import *

    Board("handpy").begin()#初始化，选择板型和端口号，不输入端口号则进行自动识别
    #Board("handpy","COM36").begin()   #windows下指定端口初始化
    #Board("handpy","/dev/ttyACM0").begin()   #linux下指定端口初始化
    #Board("handpy","/dev/cu.usbmodem14101").begin()   #mac下指定端口初始化

    rgb[0] = (255, 0, 0)  # 设置为红色，全亮度
    rgb[1] = (0, 128, 0)  # 设定为绿色，一半亮度
    rgb[2] = (0, 0, 64)   # 设置为蓝色，四分之一亮度
    rgb.write()
