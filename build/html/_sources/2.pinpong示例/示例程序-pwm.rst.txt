1-04-PWM:模拟输出
===========================================

.. code-block:: python

    # -*- coding: UTF-8 -*-
    #实验效果： PWM输出实验,控制LED灯亮度变化
    #接线：使用windows或linux电脑连接一块arduino主板，LED灯接到D6引脚上
    import time
    from pinpong.board import Board,Pin

    Board("uno").begin()               #初始化，选择板型(uno、microbit、RPi、handpy)和端口号，不输入端口号则进行自动识别
    #Board("uno","COM36").begin()      #windows下指定端口初始化
    #Board("uno","/dev/ttyACM0").begin() #linux下指定端口初始化
    #Board("uno","/dev/cu.usbmodem14101").begin()   #mac下指定端口初始化

    #pwm0 = PWM(Pin(board,Pin.D6)) #将引脚传入PWM初始化  模拟输出方法1
    pwm0 = Pin(Pin.D6, Pin.PWM) #初始化引脚为PWM模式 模拟输出方法2

    while True:
        for i in range(255):
            print(i)
            #pwm0.duty(i) #PWM输出 方法1
            pwm0.write_analog(i) #PWM输出 方法2
            time.sleep(0.05)


