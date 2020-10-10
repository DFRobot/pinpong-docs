3-05-PN532:NFC近场通讯模块
===========================================


.. code-block:: python

    # -*- coding: utf-8 -*-
    #实验效果：NFC近场通讯模块 IIC读取卡片信息
    #接线：使用windows或linux电脑连接一块arduino主控板，NFC近场通讯模块接到I2C口SCL SDA
    import time
    from pinpong.board import Board
    from pinpong.libs.dfrobot_pn532 import PN532

    Board("uno").begin()  #初始化，选择板型和端口号，不输入端口号则进行自动识别
    #Board("uno","COM36").begin()  #windows下指定端口初始化
    #Board("uno","/dev/ttyACM0").begin()   #linux下指定端口初始化
    #Board("uno","/dev/cu.usbmodem14101").begin()   #mac下指定端口初始化

    nfc = PN532()

    while not nfc.begin():
      print("initial failure")
      time.sleep(1)
    print("Please place the info card/tag on module..... ")

    while True:
      if nfc.scan():
        info = nfc.get_information()
        if info != None:
          print("----------------NFC card/tag information-------------------")
          print("UID Lenght: %d"%info.lenght)
          print("UID: %x %x %x %x"%(info.uid[0],info.uid[1],info.uid[2],info.uid[3] ))
          print("AQTA: %x %x"%(info.AQTA[0], info.AQTA[0]))
          print("SAK: 0x%x"%(info.sak))
          print("Type: %s"%(info.types))
          print("Manu facturer: %s"%(info.manu))
          print("RF Technology: %s"%(info.RF))
          print("Memory Size: %d bytes(total)/%d bytes(available)"%(info.size_total, info.size_available))
          print("Block/Page Size: %d bytes"%(info.block))
          print("Number of Blocks/pages: %d"%(info.num_block))
      time.sleep(1)


.. code-block:: python

    # -*- coding: utf-8 -*-
    #实验效果：NFC近场通讯模块 IIC读取卡片内信息
    #接线：使用windows或linux电脑连接一块arduino主控板，NFC近场通讯模块接到I2C口SCL SDA
    import time
    from pinpong.board import Board
    from pinpong.libs.dfrobot_pn532 import PN532

    Board("uno").begin()  #初始化，选择板型和端口号，不输入端口号则进行自动识别
    #Board("uno","COM36").begin()  #windows下指定端口初始化
    #Board("uno","/dev/ttyACM0").begin()   #linux下指定端口初始化
    #Board("uno","/dev/cu.usbmodem14101").begin()   #mac下指定端口初始化

    nfc = PN532()

    def print_data(block):
      value = nfc.read_data(block)
      if  value != None:
        for i in value:
          print("0x%x "%(i), end="")
        print("")
      else:
        print_data(block)

    while not nfc.begin():
      print("initial failure")
      time.sleep(1)
    print("Waiting for a card......")

    while True:
      if nfc.scan():
        NFC = nfc.get_information()
        if NFC != None:
          if NFC.lenght == 0x02 or NFC.lenght == 0x04:
            print("----------------Here is the card information to read-------------------")
            for i in range(NFC.num_block):
              if i == 0:
                print("Block %d:UID0-UID3/MANUFACTURER--------->"%(i), end="")
                print_data(i);
              elif (i+1)%4==0 and i < 128:
                print("Block %d:KEYA/ACCESS/KEYB--------------->"%(i), end="")
                print_data(i)
              elif (i+1)%16==0 and i > 127:
                print("Block %d:KEYA/ACCESS/KEYB--------------->"%(i), end="")
                print_data(i)
              else:
                print("Block %d:DATA   ------------------------>"%(i), end="")
                print_data(i)
          else:
            print("The card type is not mifareclassic...")
      time.sleep(3)
      
.. code-block:: python

    # -*- coding: utf-8 -*-
    #实验效果：NFC近场通讯模块 IIC读写卡片信息
    #接线：使用windows或linux电脑连接一块arduino主控板，NFC近场通讯模块接到I2C口SCL SDA
    import time
    from pinpong.board import Board
    from pinpong.libs.dfrobot_pn532 import PN532

    Board("uno").begin()  #初始化，选择板型和端口号，不输入端口号则进行自动识别
    #Board("uno","COM36").begin()  #windows下指定端口初始化
    #Board("uno","/dev/ttyACM0").begin()   #linux下指定端口初始化
    #Board("uno","/dev/cu.usbmodem14101").begin()   #mac下指定端口初始化

    nfc = PN532()

    write_data = "DFRobot NFC"
    #write_data = [1, 2, 3, 4, 5, 6, 7, 8, 9]
    #write_data = (10, 9, 8, 7, 6, 5, 4, 3, 2, 1)

    block_num = 2

    while not nfc.begin():
      print("initial failure")
      time.sleep(1)
    print("Waiting for a card......")

    def parse_data(read_data):
      if read_data != None:
        print("read success! data is ", end=" ")
        print(read_data)
      else:
        print("read failure!")

    while True:
      if nfc.scan():
        info = nfc.get_information()
        if info != None:
          if info.lenght == 0x02 or info.lenght == 0x04:
            if not nfc.write_data(block_num, write_data):
              print("write failure!")
            else:
              print("write success! data is", end=" ")
              print(write_data)
            read_data= nfc.read_data(block_num)
            parse_data(read_data)
          else:
            print("The card type is not mifareclassic...")
      time.sleep(2)