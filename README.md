https://stackoverflow.com/questions/2710499/android-sdk-on-a-64-bit-linux-machine/10473415
sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install libc6:i386
sudo apt-get install libsdl1.2debian:i386  //解决aapt无法运行问题!?

adb install --bypass-low-target-sdk-block example73-debug.apk


adb install -t xxxx.apk


adb shell pm list packages


在命令行中使用如下命令生成密钥库（Keystore）：

keytool -genkeypair -v -keystore my-release-key.keystore -alias my-key-alias -keyalg RSA -keysize 2048 -validity 10000

注释：

keytool 是一个用于管理密钥和证书的工具。
-genkeypair 表示生成密钥对。
-v 表示开启 verbose 模式，提供更多的信息。
-keystore 指定生成的密钥库文件名称。
-alias 是为密钥指定一个别名。
-keyalg 设置所用的加密算法（这里是RSA）。
-keysize 指定密钥的大小（这里是2048位）。
-validity 指定密钥的有效期（这里是10000天）。



在生成APK后，使用以下命令进行签名：

jarsigner -verbose -keystore my-release-key.keystore -storepass your-keystore-password -keypass your-key-password your-app.apk my-key-alias
注释：

jarsigner 是用来对JAR/AAP文件进行签名的工具。
-verbose 开启详细输出。
-keystore 指定你创建的密钥库路径。
-storepass 是密钥库的密码。
-keypass 是密钥的密码。
最后两个参数分别是要签名的APK文件和密钥别名。



使用以下命令验证APK签名：

jarsigner -verify -verbose -certs your-app.apk
注释：

-verify 用于验证APK文件的签名。
-certs 显示证书信息。




新书《Android Gradle权威指南》的示例代码

阅读地址

[Android Gradle权威指南](https://item.jd.com/12162983.html)

[https://item.jd.com/12162983.html](https://item.jd.com/12162983.html)
