2-07-neopixel:WS2812灯带
===========================================

.. code-block:: python

    # -*- coding: UTF-8 -*-
    #实验效果：控制WS2812单线RGB LED灯
    #接线：使用windows或linux电脑连接一块arduino主控板，ws2812灯接到D9口
    import time
    from pinpong.pinpong import PinPong,Pin
    from pinpong.libs.neopixel import NeoPixel #从libs中导入neopixel库


    NEOPIXEL_PIN = Pin.D9
    PIXELS_NUM = 4 #灯数

    board = PinPong("uno")  #初始化，选择板型和端口号，不输入则留空进行自动识别
    #board = PinPong("uno","COM36")  #windows下指定端口初始化
    #board = PinPong("uno","/dev/ttyS1")   #linux下指定端口初始化

    np = NeoPixel(board, Pin(board,NEOPIXEL_PIN),PIXELS_NUM)

    while True:
        np[0] = (0, 255 ,0) #设置第一个灯RGB亮度
        np[1] = (255, 0, 0) #设置第二个灯RGB亮度
        np[2] = (0, 0, 255) #设置第三个灯RGB亮度
        np[3] = (255, 0, 255) #设置第四个灯RGB亮度
        print("color 1")
        time.sleep(1)
        np[1] = (0, 255, 0)
        np[2] = (255, 0, 0)
        np[3] = (255, 255, 0)
        np[0] = (0, 0, 255)
        print("color 2")
        time.sleep(1)
