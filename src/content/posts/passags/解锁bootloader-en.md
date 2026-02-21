---
title: 联想z5解锁bootloader
published: 2025-05-29
lang: en
abbrlink: unlock-lenovo-z5-bootloader
---

### Offical website apply unlocking file

you must use 163 e-mail ,other e-mail maybe not receive unlocking mail

### FastBoot mode ,the phone not link to computer 

1. Download Drive [click here](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)
  
2. please right key click file <mark>android_winusb.inf</mark> install in the download drive. then plug the phone (in Fastboot mode) into the computer. open device manager ,and you will see an android device that is not recognized. right-click it and choose
  
    - update driver
    
    - browse my computer for driver
    
    - Let me pick from a list of available drivers on my computer

    - Select Android Bootloader Interface

    - Click Next, then Yes. The driver installation should complete successfully.

3. the device should now be recognized.


### in fastboot mode，show press any key to shutdown

- Copy the following code into a .txt file, then rename it to a .bat file and run it as Administrator:
```@echo off
@echo off
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "osvc" /t REG_BINARY /d "0000" /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "SkipContainerIdQuery" /t REG_BINARY /d "01000000" /f
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "SkipBOSDescriptorQuery" /t REG_BINARY /d "01000000" /f
pause
```
- Run the following code to remove the previous changes:

```@echo off
@echo off
reg delete "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "osvc" /f
reg delete "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "SkipContainerIdQuery" /f
reg delete "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\usbflags\18D1D00D0100" /v "SkipBOSDescriptorQuery" /f
pause
```

- If everything goes well, you should now be able to unlock your phone.