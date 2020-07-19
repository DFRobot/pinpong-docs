2-03-sr04_urm10:超声波传感器
===========================================

.. code-block:: python

    # -*- coding: UTF-8 -*-
    #实验效果：读取超声波
    #接线：使用windows或linux电脑连接一块arduino主控板，使用SR04或URM10超声波，Trig接D7，Echo接D8
    import time
    from pinpong.pinpong import PinPong,Pin
    from pinpong.libs.sr04_urm10 import SR04_URM10 #从libs中导入库


    TRIGER_PIN = Pin.D7
    ECHO_PIN = Pin.D8

    board = PinPong("uno")  #初始化，选择板型和端口号，不输入则留空进行自动识别
    #board = PinPong("uno","COM36")  #windows下指定端口初始化
    #board = PinPong("uno","/dev/ttyS1")   #linux下指定端口初始化

    sonar = SR04_URM10(board,Pin(board,TRIGER_PIN),Pin(board,ECHO_PIN))

    while True:
      dis = sonar.distance_cm() #获取距离，单位厘米(cm)
      print("distance = %d cm"%dis)
      time.sleep(0.1)
