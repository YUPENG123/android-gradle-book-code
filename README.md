https://stackoverflow.com/questions/2710499/android-sdk-on-a-64-bit-linux-machine/10473415
sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install libc6:i386
sudo apt-get install libsdl1.2debian:i386  //解决aapt无法运行问题!?

adb install --bypass-low-target-sdk-block example73-debug.apk


adb install -t xxxx.apk


adb shell pm list packages


新书《Android Gradle权威指南》的示例代码

阅读地址

[Android Gradle权威指南](https://item.jd.com/12162983.html)

[https://item.jd.com/12162983.html](https://item.jd.com/12162983.html)
