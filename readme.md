# 简介

PinPong库是一套控制开源硬件主控板的Python库，支持上百种开源硬件电子模块，5分钟即可让你上手使用Python控制开源硬件。

借助于PinPong库，直接用Python代码就能给各种常见的开源硬件，例如Arduino、树莓派、行空板。其原理是给开源硬件烧录一个特定的固件，使开源硬件可以通过串口与电脑通讯，电脑端有一套统一的Python接口库。

PinPong库的名称由“Pin”和“Pong”组成，“Pin”指引脚，“PinPong”为“乒乓球”的谐音，指信号的往复。

pinpong库的设计，是为了让开发者在开发过程中不用被繁杂的硬件型号束缚，而将重点转移到软件的实现。哪怕程序编写初期用Arduino开发，部署时改成了行空板，只要修改一下硬件的参数就能正常运行，实现了“一次编写处处运行”。

# 文档地址

https://pinpong.readthedocs.io



# 安装方法
```bash
pip install pinpong
```

# 升级方法
```bash
pip install -U pinpong
