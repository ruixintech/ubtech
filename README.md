屏蔽开源驱动nouveau

安装过程会询问是否屏蔽，手动屏蔽也有多种操作方式，

sudo gedit /etc/modprobe.d/blacklist.conf

加参数到最底下回车另起一行内容为

blacklist nouveau

options nouveau modeset=0

保存再终端更新内核命令

sudo update-initramfs -u
 
然后好了以后重启电脑
sudo apt update
sudo apt install gcc g++ make

百度nvidia 官网去下对应显卡版本的驱动举例（下面XXX是版本的意思） NVIDIA-Linux-x86_64-384.run （384或者390都可以版本里面的）下好的文件放在 主文件夹 或者说叫home 目录下

先按Ctrl + Alt + F3到控制台，关闭当前图形环境

sudo telinit 3

再安装驱动程序

 cd /home/用户名 

 进入到驱动所在文件夹 （下好的驱动文件放在home 或者叫主文件夹下）

sudo chmod a+x NVIDIA-Linux-x86_64-xxx.run
sudo sh NVIDIA-Linux-x86_64-xxx.run -no-opengl-files

最后重新启动图形环境
