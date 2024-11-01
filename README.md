# esp32cam-aliyun

ESP32-CAM 对接阿里云 IoT 平台方案

## Prerequisite

Board:

- ESP32-CAM(WiFi+蓝牙模块) + OV2640 摄像头
  - http://e.tb.cn/h.gzb20mnMa4SYIa0?tk=5K9q3LeJXtb

Arduino IDE:

- https://www.arduino.cc/en/software
- Tested Version: 2.3.3

Additional boards manager URLs:

- https://dl.espressif.com/dl/package_esp32_index.json
- Or use local version: [package_esp32_index.json](./resources/package_esp32_index.json)

Board Module:

- ESP32 Wrover Module

Libraries:

- `ArduinoJson.h`:
  - Tested Version: 7.2.0
  - Install:
    - Search `ArduinoJson - by Benoit Blanchon` from `Library Manager` then install.
  - Message:
    - https://arduinojson.org/?utm_source=meta&utm_medium=library.properties
- `PubSubClient.h`:
  - Tested Version: 2.8.0
  - Install:
    - Download zip from https://docs.arduino.cc/libraries/pubsubclient/#Releases
    - Download zip and load by `Add .ZIP Library...`
  - Message:
    - https://pubsubclient.knolleary.net/
- `SHA256.h`:
  - Tested Version: b4b722e
  - Install:
    - Download zip from https://github.com/simonratner/Arduino-SHA-256
    - Download zip and load by `Add .ZIP Library...`

3D Models:

- For Bambo A1/A1 mini: https://makerworld.com.cn/models/242156

## Configure

### Board Config

Copy `config.h.example` to `config.h` and fill in the values.

### Aliyun Config

此方案对接的是[阿里云物联网平台公共实例](https://iot.console.aliyun.com/)，而不是[生活物联网平台](https://living.aliyun.com/home)。
需要注意的是这两个平台互相冲突，如果要开通另一个平台，需要先将旧平台服务关闭。

使用阿里云物联网平台公共实例，请参考阿里云帮助中心文档：[如何在物联网平台创建产品](https://help.aliyun.com/zh/iot/user-guide/create-a-product) 创建产品和设备。

一个测试过的产品配置为：

- 所属品类：摄像头
- 节点类型：直连设备
- 连网协议：Wi-Fi
- 数据格式：ICA 标准数据格式（Alink JSON）
- 数据校验级别：弱校验
- 认证方式：设备密钥

请在产品功能定义中为物模型添加 img 功能模块：

- 类型：属性
- 功能名称：img
- 标识符：img
- 数据类型：text (字符串)
- 数据定义：数据长度：10240
- 读写类型：读写
