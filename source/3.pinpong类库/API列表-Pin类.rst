Pin类 Pin class
========================

----------------
常量 constants
----------------

--------------------
构造器 constructor 
--------------------

创建和初始化一个引脚。

pin = Pin(board, vpin, mode)

- board: 通过pinpong类创建的板子的对象。

- vpin: 板子上所用到的引脚号。(数字引脚1-Pin.D1, 模拟引脚1-PinA1)

- mode: 定义引脚的输出，输出。Pin.IN， Pin.OUT (定义模拟量引脚时省略，默认输入)

定义一个数字输入，比如按键，

button_pin = (board, Pin.D8, Pin.IN)

定义一个模拟量传感器，

Analog_pin = (board, Pin.A0)

----------------
方法 method
----------------

::

    pin.value()

    调用value()，没有提供args时，为数字读取，返回0或1。

    v = button_pin.value()//获取引脚button_pin的引脚状态

    pin.value(x)

    调用value()，提供args时，为数字写入。

    pin.value(1) //引脚pin输出高电平

::

    pin.on()
    引脚pin设置为高电平, 同pin.value(1)

::

    pin.off()
    引脚pin设置为低电平, 同pin.value(0)

::

    pin.irq(trigger,handler)
    设置中断，
    - trigger: 中断模式，rising - 上升沿, falling - 下降沿， low - 低电平， high - 高电平...
    - handler: 

