# Overlay概念
Overlays，或者硬件库，都是可编程FPGA的设计理念。通过它们，用户可以把Zynq处理系统（Processing System of the Zynq）上的应用扩展到可编程逻辑层面上。Overlays可以用来加速软件应用或者为特定的应用自定义其硬件平台。在PYNQ中可以通过python交互界面（即jupyter）来对可编程逻辑中的overlays进行控制。

PYNQ-Z2上的（base overlay）所涉及的硬件如下：

* HDMI接口（输入输出）
* Audio codec
* 4个绿色LED，2个彩色LED，两个开关，四个按钮
* 两个Pmod PYNQ Microblaze
* Arduino PYNQ Microblaze
* RPI (Raspberry Pi) PYNQ MicroBlaze
* 4个跟踪分析器（PMODA, PMODB, ARDUINO, RASPBERRYPI）

原文链接：https://blog.csdn.net/qq_34341423/article/details/102635506

# Baseoverlay概念
指那些比较基础、用于做参考设计的overlay，一般是已经烧写在sd卡上，也可以自行安装新的overlay。

# Overlay加载
1. 在jupyter工具中，通过以下代码加载指定的overlay：  
```
from pynq import Overlay
overlay = Overlay("base.bit")
 ```
2. 对于baseoverlay，则可以使用以下代码进行快速调用：
```
from pynq.overlays.base import BaseOverlay
base_overlay = BaseOverlay("base.bit")
```
base_overlay就是bit文件转化后的python类。