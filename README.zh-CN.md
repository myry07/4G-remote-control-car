# 4G-remote-control-car

语言: [English](README.md) | [简体中文](README.zh-CN.md)

这是为一家中国的玩具公司 设计的4G遥控车

## 遥控器

<p align="center">
    <img src="03.fotos/overview.png" alt="f" width="80%"/>
</p>

该遥控器采用**双MCU 架构** 支持无线控制和语音交互

### 系统架构

两个MCU之间 使用UART通信

- **ESP32-S3**  
  负责控制外设 包括:
  - 4G模组: ML307A-GCLN
  - 旋转编码器 
  - WS2812彩灯 
  - 0.96寸屏幕: SSD1306
  - 麦克风: ZTS6672S
  - 喇叭: MAX98357

- **天问 ASRPRO**  
  具有出色的**语音识别能力** 专用于语音处理

### 电源架构

该遥控器支持 **三种电源输入**:

- USB 5V
- 锂电池
- 小车 5V

对于三种输入都做了不同的输入保护 比如防倒灌 防反接  
另外使用 IP5306 实现电源管理  
由于 IP5306 对于普通5V有协议限制 充电电流被限制在了100mA  
额外搭配了一个线性充电IC SGM4056 更好地支持普通5V的充电输入

<p align="center">
  <img src="03.fotos/r.png" alt="r" width="50%" />
  <img src="03.fotos/f.png" alt="f" width="50%" />
</p>



## 小车
<p align="center">
    <img src="03.fotos/car_overview.png" alt="f" width="80%"/>
</p>


### 系统架构

使用**ESP8266** 作为主控 外设包括:  
  - H-Bridge: SA8302
  - 6-Axis-IMU: QMI8658B
  - WS2812彩灯
  
### 电源架构

该小车使用 IP5306 进行电源管理  
支持 USB 5V 和 锂电池 输入  
并引出了5V 输出接口 给遥控器充电


<p align="center">
  <img src="03.fotos/car_f.png" alt="r" width="70%" />
  <img src="03.fotos/car_r.png" alt="f" width="70%" />
</p>
