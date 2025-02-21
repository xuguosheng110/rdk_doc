---
sidebar_position: 0
---

# D-Robotics RDK套件

本文档为D-Robotics RDK套件的用户手册，为开发者提供关于RDK X3（旭日X3派）、RDK X3 Module（旭日X3模组）、RDK X5 、RDK Ultra等产品的使用说明和开发指导，内容涵盖硬件设计、系统定制、应用开发、算法工具链等多个方面。欢迎用户使用，具体方法请参考 [系统烧录](./01_Quick_start/install_os.md) 章节。

:::info 注意

- 本文档中**RDK X3**均使用3.0 & 2.0版本Ubuntu操作系统，对于仍需使用**旭日X3派1.0版本系统**的用户，可从下述链接中获取资料：<br/>
     [旭日X3派用户手册](https://developer.d-robotics.cc/api/v1/fileData/documents_pi/index.html)<br/>
     [旭日X3派Ubuntu镜像](https://archive.d-robotics.cc/downloads/os_images/)，选择1.x.x 版本目录下的镜像<br/>
     [旭日X3派资料包](https://developer.d-robotics.cc/api/v1/static/fileData/X3%E6%B4%BE%E8%B5%84%E6%96%99%E5%8C%85_20220711175326.zip)<br/>

-  **RDK X3 Module**出厂已经烧写测试版本系统镜像，为确保使用最新版本的系统，建议参考本文档完成[系统烧录](./01_Quick_start/install_os.md)。

用户如需确认系统版本号，可通过该命令查询 `cat /etc/version`, 2.1.0 及以上版本可以通过 `rdkos_info` 命令查看具体的版本信息。
:::



## D-Robotics RDK套件概述

**D-Robotics Developer Kits**，简称 RDK 套件，是基于 D-Robotics 智能芯片打造的机器人开发者套件，包括 RDK X3（旭日X3派）、RDK X3 Module（旭日X3模组）、RDK X5、RDK Ultra。

搭配 TogetheROS.Bot 机器人中间件，RDK 套件可以帮助发者快速搭建机器人原型，开展评测和验证工作。

本文将详细说明 RDK 套件的使用方法，包括开发环境搭建、示例教程的运行、应用程序的开发、系统镜像的定制等方面内容。无论您选择使用哪种硬件，本文所介绍的内容都将为您提供一致的使用体验。

## 产品介绍

**RDK X3（旭日X3派）** 是一款全功能开发板，具有 5Tops 端侧推理算力。通过搭配丰富的传感器和扩展组件，为开发者提供了灵活的硬件扩展和连接选项。

**RDK X3 Module（旭日X3模组）** 是一款紧凑型核心模组，与 RDK X3 保持了同等规格，尺寸和接口兼容树莓派 CM4 模组。通过搭配扩展板，可以为各种应用场景提供高效的计算和通信能力。

**RDK X5** 是一款全功能开发板，具有 10Tops 端侧推理算力与 8 核 ARM A55 处理能力，支持 2 路 MIPI Camera 接入，4 路 USB3.0 接口。通过搭配丰富的传感器和扩展组件，为开发者提供了灵活的硬件扩展和连接选项。

**RDK Ultra** 是一款高性能开发套件，具有 96Tops 端侧推理算力与 8 核 ARM A55 处理能力，支持 4 路 MIPI Camera 接入，4 路 USB3.0 接口，3 路 PCIe3.0 接口，充分满足各类场景的使用需求。

![image-rdk-serials](../static/img/image-rdk-serials.jpg)


## 文档使用指引

下面将对用户手册的整体内容划分进行介绍，帮助用户快速了解文档的结构和内容，以便更好地利用文档进行开发、学习工作。

**一、快速开始**  
介绍系统安装，硬件接口使用的入门说明，帮助用户快速上手使用开发板。  

**二、系统配置**  
介绍一系列配置步骤和技巧，以确保系统能够正常工作并满足特定的需求，引导用户进行系统的配置，包括系统升级、网络、蓝牙的配置。  

**三、基础应用开发**  
介绍系统中预装的功能示例，如 IO 管脚控制、音视频采集，多媒体初步使用等。  

**四、算法应用开发**  
介绍Python和C++两种语言版本的算法简易接口的使用方法，此接口简单易用，方便用户快速上手，基于更底层的推理接口进行了封装，并提供基础的使用示例。  

**五、机器人应用开发**  
向机器人厂商和生态开发者推出的机器人操作系统，旨在释放机器人场景的智能潜能，助力生态开发者和商业客户能够高效、便捷的进行机器人开发，打造具有竞争力的智能机器人产品。

**六、应用开发指南**  
包含了深度学习寻线小车、AMR开发指南，大模型应用等多方面的应用开发指南。

**七、进阶开发**  
完整的介绍了硬件开发、系统开发、多媒体应用开发以及算法开发指南，涵盖了硬件设计，系统配置编译，多媒体使用与调试，算法训练与量化上板的开发流程，接口功能丰富，可以实现复杂、灵活的功能需求。

**八、常见问题**  
本章节回答了用户在使用开发者套件过程中可能遇到的常见问题和疑惑。它提供了解决方案和技巧，帮助用户解决常见问题并顺利进行开发工作。

**九、附录**  
本章节提供 RDK OS 中常用的命令用法，其中 RDK 专属命令可以帮助用户获取、查询系统的一些关键信息。

## 版本发布记录

### 版本号：3.0.0

新增功能：

- 支持 ubuntu 22.04
- 支持新套件 RDK X5

### 版本号：2.1.0

新增功能：

- 完善srpi-config系统配置工具，支持Wi-Fi连接，开/关SSH、VNC，使能/禁用40pin上的外设总线，本地化语言配置，设置CPU超频，设置ION内存大小等系统配置。
- 支持了/boot/config.txt系统配置文件，支持设置dtoverlay、cpu超频、io启动状态配置等选项。
- 添加yolov5s v6/v7 模型示例。

优化改进：

- 支持在hdmi显示器上输出启动日志和进入用户命令行，方便用户使用。
- 支持更多的hdmi显示分辨率，极大的增强了兼容性。
- 优化了Desktop和server版本的预装软件清单，删除冗余项，补充必要软件，如添加vlc。
- 优化了Desktop菜单栏的布局，精简选项。
- 默认开启蓝牙功能。
- 增加后处理的C++接口，提高后处理效率。
- 使用udisk2自动挂载U盘，解决NTFS文件系统自动挂载后不能访问的问题。
- 支持用户保留vnc密码文件。
- VNC服务默认不自动开启，可以减少系统的资源消耗。用户可以通过srpi-config工具打开。
- RDK X3 v2.1和RDK Module开发板CPU正常模式下最高运行在1.5GHz频率，超频后最高运行频率1.8GHz

问题修复：

- 删除Wi-Fi驱动的冗余内核日志。
- 修改apt源域名为archive.d-robotics.cc

其他更新：

- 支持 chromium 浏览器，用户可以使用 `sudo apt install chromium` 安装使用。

### 版本号：2.0.0

这次发布带来了许多令人期待的功能和改进，旨在提供更好的开发体验和更广泛的应用场景支持。以下是本次版本发布的主要亮点：

开放源代码：

- 我们完全开放了操作系统的源代码，包括系统核心模块和功能模块的源代码。开发者可以自由地查看和修改源代码，为定制化和优化提供了更大的灵活性。
- 详细的代码文档和注释将提供给开发者，以帮助他们更好地理解和使用源代码。
- 我们欢迎开发者通过开源社区参与代码贡献和讨论，共同推动操作系统的改进和优化，源码在 [D-Robotics](https://github.com/D-Robotics) 上维护。

支持RDK X3 Module：

- 我们引入了全新的核心板开发者套件，RDK X3 Module。
- RDK X3 Module拥有更小的尺寸，并兼容树莓派CM4接口。
- 开发者可以根据需求选择适配的第三方载板，从而扩展核心板的功能和应用场景。

其他更新：

- 我们对已有功能进行了优化，修复了已知问题和漏洞，提升了操作系统的稳定性和性能。
- 修订了文档和帮助文档，提供更全面、准确的技术资料和指南。
- 我们提供了更低层的API，方便开发者进行二次开发和集成，使其能够更加灵活地定制软件。