掌控板示例-音乐播放
===========================================

.. code-block:: python

    # -*- coding: UTF-8 -*-
    #实验效果：控制掌控板蜂鸣器播放音调
    #接线：使用windows或linux电脑连接一块掌控板主控板

    import time
    from pinpong.board import Board
    from pinpong.extension.handpy import *

    Board("handpy").begin()#初始化，选择板型和端口号，不输入端口号则进行自动识别
    #Board("handpy","COM36").begin()   #windows下指定端口初始化
    #Board("handpy","/dev/ttyACM0").begin()   #linux下指定端口初始化
    #Board("handpy","/dev/cu.usbmodem14101").begin()   #mac下指定端口初始化

    tune = ["C4:4", "D4:4", "E4:4", "C4:4", "C4:4", "D4:4", "E4:4", "C4:4",
            "E4:4", "F4:4", "G4:8", "E4:4", "F4:4", "G4:8"]
    music.play(tune)                #播放自编乐谱

