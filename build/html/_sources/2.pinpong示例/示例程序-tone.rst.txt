2-01-tone:蜂鸣器
===========================================


.. code-block:: python

    # -*- coding: UTF-8 -*-
    #实验效果：控制蜂鸣器发声
    #接线：使用windows或linux电脑连接一块arduino主控板，主控板D8接一个蜂鸣器模块
    import time
    from pinpong.pinpong import PinPong,Pin
    from pinpong.libs.tone import Tone  #从libs下导入Tone类实现控制蜂鸣器

    board = PinPong("uno")  #初始化，选择板型和端口号，不输入则留空进行自动识别
    #board = PinPong("uno","COM36")  #windows下指定端口初始化
    #board = PinPong("uno","/dev/ttyS1")   #linux下指定端口初始化

    tone = Tone(board, Pin(board,Pin.D8)) #将Pin传入Tone中实现模拟输出
    tone.freq(200) #按照设置的频率播放

    '''
    while True:
      tone.tone(200,500)  #按照设置的频率和时间播放直到完成
      time.sleep(1)
    '''

    while True:
      print("freq=",tone.freq()) #读取频率并打印
      tone.on()  #打开蜂鸣器
      time.sleep(1) 
      tone.off() #关闭蜂鸣器
      time.sleep(1)
      tone.freq(tone.freq()+100) #按照设置的频率播放