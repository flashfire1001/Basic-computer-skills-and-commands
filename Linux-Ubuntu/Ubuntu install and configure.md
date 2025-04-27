## Ubuntu 22.04/24.04 install and configure

----

#### 1.卸载原有的24.04ubuntu（非必要）

```
在windows的磁盘管理中，删除之即可
```



#### 2.ventoy 下载；U盘格式化；U盘导入iso文件

ventoy 下载 - 启动 ventoyPluginson 把全局控制语言改成中文；制定搜索目录 U:\ISO



####3.备份好你的windows；格式化一个磁盘/压缩磁盘，为Linux留空间

此电脑 - 磁盘管理 - 压缩或者格式化释放空间

建议C盘 — 最快最流畅

#### 4.BIOS模式启动；关闭安全模式；把U盘设置为第一启动项

重启按F2/F10 进入BIOS面板 

关闭安全模式后，把U盘设置为第一启动项，保存退出，继续启动进程。

#### 5.安装Ubuntu；分出各个盘

/30G

/swap 8G （逻辑分区）

/home 60G（多多益善）

/EFI 512 MB（双系统这个不需要）

####6.配置ubuntu；配置grub页面；配置输入法、桌面、系统语言、源

```
sudo passwd root
sudo apt update
sudo apt purge ibus（可选）
sudo nano /etc/default/grub
GRUB_DEFAULT=0
GRUB_TIMEOUT_STYLE=hidden
GRUB_TIMEOUT=10
GRUB_DISTRIBUTOR=`( . /etc/os-release; echo ${NAME:-Ubuntu} ) 2>/dev/null || ec>
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
GRUB_CMDLINE_LINUX=""
GRUB_GFXMODE=1024x768


修改：
sudo update-grub 保存 
换源 - 软件与更新 - 其他 - 选一个

语言支持 -可以切换成企鹅5（Fcitx5）
设置侧栏不显示卷 在设置-ubuntu 桌面中操作

设置文件夹为英语 在语言支持中改为英语 - 拉到最上 -应用到系统 
此外，在设置中语言和地区也改为US 此后注销重新进入

设置开机直接登陆 用户中设置 
关闭终端声音

```

#### 7.软件安装配置（ROS Vscode gcc gdb Clash Typora）

```text
sudo apt install gedit -y

sudo apt install build-essential
# check: gcc --version
sudo apt install gdb 
sudo apt install valgrind


ROS:
使用fishros的一键安装
wget http://fishros.com/install -O fishros && . fishros

wget https://fishros.com/install -O fishros && . fishros

教学视频   ----https://www.bilibili.com/video/BV1Jz421B7Ey?vd_source=f0077d9951e2a04efcd48cadfe421dec&spm_id_from=333.788.videopod.sections
whereis ros2 查看目录
```



Enjoy your new OS!

