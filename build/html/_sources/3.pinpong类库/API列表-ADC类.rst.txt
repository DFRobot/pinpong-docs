ADC类 ADC class
========================

---------------------
构造器 constructor 
---------------------

创建和初始化一个ADC,获取模拟量数据。

adc = ADC(board,Pin(board, Pin.A0))

- board: 通过pinpong类创建的板子对象。

- Pin: 通过pin类创建的引脚对象。

----------------
方法 method
----------------

::

    adc.read()
    读取adc的模拟量。比如，brightness = adc.read()


