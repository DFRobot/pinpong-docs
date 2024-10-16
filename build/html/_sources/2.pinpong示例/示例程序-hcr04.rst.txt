2-03-sr04_urm10:超声波传感器
===========================================

.. code-block:: python

    # -*- coding: UTF-8 -*-
    #实验效果：读取超声波
    #接线：使用windows或linux电脑连接一块arduino主控板，使用SR04或URM10超声波，Trig接D7，Echo接D8
    import time
    from pinpong.board import Board,Pin,SR04_URM10 #中导入SR04_URM10

    Board("uno").begin()               #初始化，选择板型(uno、leonardo、xugu)和端口号，不输入端口号则进行自动识别
    #Board("uno","COM36").begin()      #windows下指定端口初始化
    #Board("uno","/dev/ttyACM0").begin() #linux下指定端口初始化
    #Board("uno","/dev/cu.usbmodem14101").begin()   #mac下指定端口初始化

    TRIGER_PIN = Pin(Pin.D7)
    ECHO_PIN = Pin(Pin.D8)

    sonar = SR04_URM10(TRIGER_PIN,ECHO_PIN)

    while True:
      dis = sonar.distance_cm() #获取距离，单位厘米(cm)
      print("distance = %d cm"%dis)
      time.sleep(0.1)
