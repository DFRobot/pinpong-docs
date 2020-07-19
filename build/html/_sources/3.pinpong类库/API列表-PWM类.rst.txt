PWM类 PWM class
=======================

--------------------
构造器 constructor 
--------------------

创建和初始化一个PWM, 来输出PWM信号。

pwm0 = PWM(board, Pin(board, Pin.D6))

- board: 通过pinpong类创建的板子对象。

- Pin: 通过pin类创建的引脚对象。

----------------
方法 method
----------------

::

    pwm0.freq()
    freq()，没有提供args时，返回频率。
    f = pwm0.freq()//获取PWM频率。
    pwm0.freq(x)
    freq(x)，提供args时，设置PWM频率为x。
    pwm0.freq(1000)//设置PWM频率为1000。

::

    pwm0.duty()
    duty()，没有提供args时，返回占空比。
    f = pwm0.duty()//获取PWM占空比。
    pwm0.duty(x)
    duty(x)，提供args时，设置PWM占空比，范围0-255。
    pwm0.duty(127)//设置PWM占空比为50%。

::

    pwm0.deinit()
    


