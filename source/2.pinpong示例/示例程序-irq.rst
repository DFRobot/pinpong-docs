1-05-irq:引脚中断
===========================================

.. code-block:: python

    # -*- coding: UTF-8 -*-
    #实验效果：引脚模拟中断功能测试
    #接线：使用windows或linux电脑连接一块arduino主控板，主控板D8接一个按钮模块
    import time
    from pinpong.pinpong import PinPong,Pin

    board = PinPong("uno")  #初始化，选择板型和端口号，不输入则留空进行自动识别
    #board = PinPong("uno","COM36")  #windows下指定端口初始化
    #board = PinPong("uno","/dev/ttyS1")   #linux下指定端口初始化


    btn = Pin(board, Pin.D8, Pin.IN)

    def btn_handler(data):#中断事件回调函数
      print("\n-----")
      print("pin_mode = ", data[0]) 
      print("pin = ", data[1])
      print("value = ", data[2])

    #btn.irq(trigger=Pin.IRQ_FALLING, handler=btn_handler) #设置中断模式为下降沿触发
    btn.irq(trigger=Pin.IRQ_RISING, handler=btn_handler) #设置中断模式为上升沿触发，及回调函数
    #btn.irq(trigger=Pin.IRQ_RISING+Pin.IRQ_FALLING, handler=btn_handler) #设置中断模式为电平变化时触发

    while True:
      time.sleep(1) 

