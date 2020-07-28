1-05-irq:引脚中断
===========================================

.. code-block:: python

    # -*- coding: UTF-8 -*-
    #实验效果：引脚模拟中断功能测试
    #接线：使用windows或linux电脑连接一块arduino主控板，主控板D8接一个按钮模块
    
    import time
    from pinpong.board import Board,Pin

    Board("uno").begin()               #初始化，选择板型(uno、leonardo、xugu)和端口号，不输入端口号则进行自动识别
    #Board("uno","COM36").begin()      #windows下指定端口初始化
    #Board("uno","/dev/ttyACM0").begin() #linux下指定端口初始化
    #Board("uno","/dev/cu.usbmodem14101").begin()   #mac下指定端口初始化

    btn = Pin(Pin.D8, Pin.IN)

    def btn_rising_handler(pin):#中断事件回调函数
      print("\n--rising---")
      print("pin = ", pin)
      
    def btn_falling_handler(pin):#中断事件回调函数
      print("\n--falling---")
      print("pin = ", pin)

    def btn_both_handler(pin):#中断事件回调函数
      print("\n--both---")
      print("pin = ", pin)

    btn.irq(trigger=Pin.IRQ_FALLING, handler=btn_falling_handler) #设置中断模式为下降沿触发
    #btn.irq(trigger=Pin.IRQ_RISING, handler=btn_rising_handler) #设置中断模式为上升沿触发，及回调函数
    #btn.irq(trigger=Pin.IRQ_RISING+Pin.IRQ_FALLING, handler=btn_both_handler) #设置中断模式为电平变化时触发

    while True:
      time.sleep(1) #保持程序持续运行

