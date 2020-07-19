2-02-servo:舵机
===========================================

.. code-block:: python


	# -*- coding: UTF-8 -*-
    #实验效果：舵机控制
    #接线：使用windows或linux电脑连接一块arduino主控板，D4连接一个舵机
    import time
    from pinpong.pinpong import PinPong,Pin
    from pinpong.libs.servo import Servo #从libs中导入Servo库

    board = PinPong("uno")  #初始化，选择板型和端口号，不输入则留空进行自动识别
    #board = PinPong("uno","COM36")  #windows下指定端口初始化
    #board = PinPong("uno","/dev/ttyS1")   #linux下指定端口初始化

    s1 = Servo(board, Pin(board,Pin.D4)) #将Pin传入Servo中初始化舵机引脚

    while True:
		s1.angle(0) #控制舵机转到0度位置
		print("0")
		time.sleep(1)

		s1.angle(90) #控制舵机转到90度位置
		print("90")
		time.sleep(1)

		s1.angle(180) #控制舵机转到180度位置
		print("180")
		time.sleep(1)

		s1.angle(90) #控制舵机转到90度位置
		print("90")
		time.sleep(1)