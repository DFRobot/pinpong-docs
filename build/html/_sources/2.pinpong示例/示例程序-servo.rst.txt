2-02-servo:舵机
===========================================

.. code-block:: python

		# -*- coding: UTF-8 -*-
		#实验效果：舵机控制
		#接线：使用windows或linux电脑连接一块arduino主控板，D4连接一个舵机
		import time
		from pinpong.board import Board,Pin,Servo #导入Servo库

		Board("uno").begin()               #初始化，选择板型(uno、microbit、RPi、handpy)和端口号，不输入端口号则进行自动识别
		#Board("uno","COM36").begin()      #windows下指定端口初始化
		#Board("uno","/dev/ttyACM0").begin() #linux下指定端口初始化
		#Board("uno","/dev/cu.usbmodem14101").begin()   #mac下指定端口初始化

		s1 = Servo(Pin(Pin.D4)) #将Pin传入Servo中初始化舵机引脚

		while True:
			#s1.angle(0) #控制舵机转到0度位置 方法1
			s1.write_angle(0)  #控制舵机转到0度位置 方法2
			print("0")
			time.sleep(1)

			#s1.angle(90) #控制舵机转到90度位置
			s1.write_angle(90)  #控制舵机转到90度位置 方法2
			print("90")
			time.sleep(1)

			#s1.angle(180) #控制舵机转到180度位置
			s1.write_angle(180)  #控制舵机转到180度位置 方法2
			print("180")
			time.sleep(1)

			#s1.angle(90) #控制舵机转到90度位置
			s1.write_angle(90)  #控制舵机转到90度位置 方法2
			print("90")
			time.sleep(1)