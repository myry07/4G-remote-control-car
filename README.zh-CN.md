# 4G-remote-control-car


语言: [English](README.md) | [简体中文](README.zh-CN.md)



## 遥控器

<p align="center">
    <img src="03.fotos/overview.png" alt="f" width="80%"/>
</p>

该遥控器采用**双MCU 架构** 支持无线控制和语音交互

### MCU 架构

两个MCU之间 使用UART通信

- **ESP32-S3**  
  负责控制外设 包括:
  - 4G模组: ML307A-GCLN
  - 旋转编码器  
  - 0.96寸屏幕: SSD1306
  - 麦克风: ZTS6672S
  - 喇叭: MAX98357

- **天问 ASRPRO**  
  具有出色的**语音识别能力** 专用于语音处理

### 供电方案

该遥控器支持 **三种电源输入**:

- **USB 5V**
- **锂电池**
- **小车 5V**

对于三种输入都做了不同的输入保护 比如防倒灌 防反接  
另外使用 IP5306 实现电源管理


<p align="center">
  <img src="03.fotos/r.png" alt="r" width="50%" />
  <img src="03.fotos/f.png" alt="f" width="50%" />
</p>




## Car
<p align="center">
    <img src="03.fotos/car_overview.png" alt="f" width="80%"/>
</p>



### MCU Architecture

- **ESP8266**  
  Responsible for controlling peripherals, including:
  - H-Bridge  
  - 6-Axis-IMU  
  - WS2812  


<p align="center">
  <img src="03.fotos/car_f.png" alt="r" width="70%" />
  <img src="03.fotos/car_r.png" alt="f" width="70%" />
</p>


