1-02-button:数字输入
===========================================

.. code-block:: python

    # -*- coding: UTF-8 -*-
    #实验效果：使用按钮控制arduino UNO板载亮灭
    #接线：使用windows或linux电脑连接一块arduino主控板，主控板D8接一个按钮模块
    import time
    from pinpong.pinpong import PinPong,Pin

    board = PinPong("uno")  #初始化，选择板型和端口号，不输入则留空进行自动识别
    #board = PinPong("uno","COM36")  #windows下指定端口初始化
    #board = PinPong("uno","/dev/ttyS1")   #linux下指定端口初始化

    btn = Pin(board, Pin.D8, Pin.IN) #引脚初始化为电平输入
    led = Pin(board, Pin.D13, Pin.OUT)

    while True:
      #v = btn.value()  #读取引脚电平方法1
      v = btn.read_digital()  #读取引脚电平方法2
      print(v)  #终端打印读取的电平状态
      #led.value(v)  #将按钮状态设置给led灯引脚  输出电平方法1
      led.write_digital(v) #将按钮状态设置给led灯引脚  输出电平方法2
      time.sleep(0.1)
