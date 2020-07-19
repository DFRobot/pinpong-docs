1-01-blink:数字输出
===========================================

.. code-block:: python

    # -*- coding: UTF-8 -*-
    #实验效果：控制arduino UNO板载LED灯一秒闪烁一次
    #接线：使用windows或linux电脑连接一块arduino主控板
    import time
    from pinpong.pinpong import PinPong,Pin

    board = PinPong("uno")  #初始化，选择板型和端口号，端口留空则自动识别端口，适合只有一块uno板
    #board = PinPong("uno","COM36")  #windows下外接开发板时指定端口初始化
    #board = PinPong("uno","/dev/ttyS1")   #linux下外接开发板时指定端口初始化

    led = Pin(board, Pin.D13, Pin.OUT) #引脚初始化为电平输出

    while True:
      #led.value(1) #输出高电平 方法1
      led.write_digital(1) #输出高电平 方法2
      print("1") #终端打印信息
      time.sleep(1) #等待1秒 保持状态

      #led.value(0) #输出低电平 方法1
      led.write_digital(0) #输出低电平 方法2
      print("0") #终端打印信息
      time.sleep(1) #等待1秒 保持状态


        
