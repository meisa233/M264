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
When you see "Dell" Symbol, you can press "Esc". Next you should select the old kernel.
