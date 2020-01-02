# 一、平台架构

Android是一种基于Linux的开放源代码软件栈。

主要组件

![Android 软件堆栈](https://developer.android.google.cn/guide/platform/images/android-stack_2x.png)

##  Linux内核

Android平台的基础是Linux内核，Android runtime（ART）依靠Linux内核来执行底层功能，如线程和底层内存管理。

##  硬件抽象层（HAL）

硬件抽象层（HAL）提供标准界面，向更高级别 Java API框架显示设备硬件功能，HAL包含多个库模块，其中每个模块都为特定类型的硬件组件实现一个界面，

## Android runtime

每个应用都在其自己的进程中运行，并且有其自己的Android runtime（ART）实例。ATR编写为通过执行DEX文件在低内存设备上运行多个虚拟机，DEX文件是一种专为Android设计的字节码格式，编译工具链（如 Jack）将 Java源代码编译为DEX字节码，使其可在Android平台上运行。

ART的部分主要功能包括：

* 预先（AOT）和即时（JIT）编译
* 优化的垃圾回收（GC）
* 在Android 9（API 级别28）及更高版本的系统中，支持将软件包中的Dalvik Executable格式（DEX）文件转化为更紧凑的机器代码
* 更好的调试支持，包括专用采样分析器、详细的诊断异常和崩溃报告，并且能够设置观察点以监控特定字段

## 原生C/C++库

许多核心Android系统组件和服务（如ART和HAL）构建自原生代码，需要以C和C++编写的原生库。Android平台提供 Java框架API以向应用显示其中部分原生库的功能。例如，通过Android 框架的Java OpenGL API访问OpenGL ES，以支持在应用中绘制2D、3D图形。

开发需要C/C++代码的应用，可以使用Android NDK直接从原生代码访问某些原生平台库。

## Java API框架

使用 Java语言编写的API使用整个Android的功能，API形成创建Android应用所需的构建块，他们可简化核心模块化系统组件和服务的重复使用，包括以下组件和服务;

* view系统，可以构建应用的UI，包括列表、网格、文本框、按钮。
* 资源管理器，用于访问非代码资源，例如本地化的字符串、图形和布局文件。
* 通知管理器，可让所有应用在状态栏中显示自定义提醒。
* Activity管理器，用于管理应用的生命周期，提供常见的导航返回栈。
* 内容提供程序，可让应用访问其他应用（如联系人应用）中的数据或者共享其自己的数据

## 系统应用

Android随附一套用于电子邮件、短信、日历、互联网浏览和联系人等的核心应用。用户可以选择替换默认应用，有些应用如设置则不能替换。

# 二、通用系统映像（GSI）

 通用系统映像（GSI）是一个“纯Android”实现，采用未经修改的Android开源项目（AOSP）代码，运行在各种设备上。

GSI适用于以下特征的设备：

* 引导加载程序已解锁

* 完全符合Treble要求

  检查是否支持Treble 命令 adb shell getprop ro.treble.enabled

  检查是否支持跨版本安装   adb shell cat /system/etc/ld.config.version_identifier.txt \  | grep -A 20 "\\[vendor\\]"

* API 28及以上

* cpu架构和GSI类型相同。

# 三、动态系统更新（DSU）

动态系统更新（DSU）是Android Q中引入的系统功能，可以执行以下操作：

* 将新的GSI或其他Android系统下载到设备上
* 创建新的动态分区
* 将GSI加载到新的分区
* 在设备上将GSI作为来宾操作系统启动

DSU还可以让你在当前系统映像和GSI之间切换，在试用GSI时不会面临当前系统映像受损的风险。

DSU依赖于Android动态分区功能，并要求GSI作为可信系统映像由Google和OEM进行签名，DSU是设备制造商提供的功能。

启用DSU功能：adb shell setprop persist.sys.fflag.override.settings_dynamic_system true

启动DSU（非稀疏映像）：

```gzip -c system_raw.img > system_raw.gz ```

```adb push system_raw.gz /storage/emulated/0/Download/```

```adb shell am start-activity \
    -n com.android.dynsystem/com.android.dynsystem.VerificationActivity  \
    -a android.os.image.action.START_INSTALL    \
    -d file:///storage/emulated/0/Download/system_raw.gz  \
    --el KEY_SYSTEM_SIZE $(du -b system_raw.img|cut -f1)  \
    --el KEY_USERDATA_SIZE 8589934592```
```

点击restart以启动到GSI

点击discard以清理GSI

粘滞模式

当您利用 GSI 完成应用验证后，您可以执行代码重新启动以将系统重新启动到原始操作系统。

要设置在下次重新启动时使用 GSI，您可以启用粘滞模式，让 GSI 在多个启动周期内保持安装状态（直至舍弃），也可以停用粘滞模式，将其仅用于一个启动周期。

以下命令可启用粘滞模式：

```
adb shell gsi_tool enable
```

以下命令可停用粘滞模式：

```
adb shell gsi_tool disable    adb shell gsi_tool enable -s    adb shell gsi_tool disable
```

#  四、系统安全性

运行时设置权限

配置网络安全设置

更新为直接启动感知型

# 五、Android App Bundle

Android App Bundle是Android新推出的一种官方发布格式，可以更高效的方式开发和发布应用，以更小的应用提供更优质的服务，从而提升安装成功率并减少卸载量。

在 Android Studio 3.2 或更高版本、Unity 2018.3 与 2017.4.17，以及 Cocos Creator 2.0.9 或更高版本中受支持。



* 更高效管理版本
* 更小的应用|Google play 的Dynamic Delivery
* 自定义功能传送
* 提升工程速度
* 缩短编译时间
* 提供Google play instant 免安装体验

