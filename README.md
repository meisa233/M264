# M264
Ubuntu 20.04
## 1.Install an old kernel
https://askubuntu.com/questions/700214/how-do-i-install-an-old-kernel <br />
Download old kernel files from http://kernel.ubuntu.com/~kernel-ppa/mainline/ <br />
For example, we can download amd64/linux-headers-5.8.18-050818-generic_5.8.18-050818.202011011237_amd64.deb, amd64/linux-headers-5.8.18-050818_5.8.18-050818.202011011237_all.deb, amd64/linux-image-unsigned-5.8.18-050818-generic_5.8.18-050818.202011011237_amd64.deb and amd64/linux-modules-5.8.18-050818-generic_5.8.18-050818.202011011237_amd64.deb from
https://kernel.ubuntu.com/~kernel-ppa/mainline/v5.8.18/ <br />
Download and put them in specified folder
```
sudo dpkg -i *.deb
```
Edit "/etc/default/grub"
```
GRUB_TIMEOUT=0 ---> #GRUB_TIMEOUT=0
```
```
sudo update-grub
```
When you see "Dell" Symbol, you can press "Esc". Next you should select the old kernel. <br />
Better option: <br />
https://blog.csdn.net/hfutdog/article/details/79331949 <br />

## 2.Install java
https://blog.csdn.net/zbj18314469395/article/details/86064849 <br />

从Oracle官方网站下载jdk包（>=8版本的），这里下的 8（jdk1.8.0_311）<br />
在/usr/lib/下创建jvm文件夹，然后把压缩包解压到jvm文件夹下
```
sudo tar -zxvf ~/下载/jdk-8u311-linux-x64.tar.gz -C /usr/lib/jvm
```
在~/.bashrc里添加如下内容
```
export JAVA_HOME=/usr/lib/jvm/jdk1.8.0_311
export JRE_HOME=${JAVA_HOME}/jre
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH
```
使变量马上生效
```
source ~/.bashrc
```
在系统注册此jdk
```
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk1.8.0_311/bin/java 300
```
