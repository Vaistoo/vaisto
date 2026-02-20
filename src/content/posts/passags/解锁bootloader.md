---
title: 联想z5解锁bootloader
published: 2025-05-25
lang: zh
abbrlink: unlock-lenovo-z5-bootloader
---

### 官网申请解锁文件

这里需要注意尽量使用163邮箱，其他邮箱好像接收不到

### FastBoot模式下识别不到设备

1. 下载驱动 [点这里哦](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)
  
2. 将文件中的 <mark>android_winusb.inf</mark> 右键点击安装，随后将fastboot模式下的手机插在电脑上，此时打开设备管理器，会发现有一个android设备显示无法识别，这时右键点击选择
  
    - 更新驱动选项
    
    - 浏览计算机以查找驱动程序软件
    
    - 让我从计算机上的可用驱动程序列表中选取

    - 选择 Android bootloader interface

    - 随后下一步，是，这时显示驱动更新完成

3. 此时设备即可识别


### 在fastboot模式下，显示 press any key to shutdown

- 将下面的代码复制到txt文本中然后改为.bat文件，以管理员身份运行
```@echo off
@echo off
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "osvc" /t REG_BINARY /d "0000" /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "SkipContainerIdQuery" /t REG_BINARY /d "01000000" /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "SkipBOSDescriptorQuery" /t REG_BINARY /d "01000000" /f
pause
```
- 运行以下代码可以删除之前的更改

```@echo off
@echo off
reg delete "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "osvc" /f
reg delete "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "SkipContainerIdQuery" /f
reg delete "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "SkipBOSDescriptorQuery" /f
pause
```

- 不出意外现在可以解锁你的手机了