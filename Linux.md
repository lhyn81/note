---
title: Linux Note
tags: Linux, Ubuntu, Pi
---

[toc]

---
## Ubuntu

### 设置系统时间
```
sudo cp /usr/share/zoneinfo/Asia/ShangHai /etc/localtime #设置时区，防止系统重启后时区改变
sudo apt-get install ntpdate #安装ntpdate工具
ntpdate cn.pool.ntp.org #设置系统时间与网络时间同步
hwclock –systohc #将系统时间写入硬件时间
```

## Pi

### Mjpg-streamer
1. 安装依赖包
```
sudo apt-get install cmake libjpeg8-dev imagemagick libv4l-dev
```
2. 获取源程序
```
cd ~/work
git clone https://github.com/jacksonliam/mjpg-streamer.git #Rasbian自带Git
```
3. 编译程序
```
cd ~/work/mjpg-streamer
cd mjpg-streamer-experimental
make
sudo make install
```
4. 开启服务
```
export LD_LIBRARY_PATH=.
./mjpg_streamer -o "output_http.so -w ./www" -i "input_raspicam.so"
```
5.在浏览器输入
```
http://121.195.160.227:8080
```

### GPIO图例
![image](http://www.th7.cn/d/file/p/2016/05/23/9c64a32fdb5ff6c261c7814ac52110b3.jpg)

### 自动拍照的实现
参阅相关资源
有几点需要注意：  
1 需要将init.d下的脚本和py文件都设置777权限  
2 需要在py文件中标明 #! usr/bin/python 这样才可以在脚本中用./执行。  
3 脚本中最好用&转为后台执行，不阻塞其他进程  
4 sudo update-rc.d camera defaults 将服务更新到开机启动列表

3. 查看服务状态

```
1. ps -aux  ｜ grep xxx  #是查看某个进程或者服务是否存在。
2. chkconfig --list 
3. service 服务名 status   #查看指定服务的运行状态
```
### 设置samba服务

```
安装软件：
sudo apt-get install samba samba-common-bin
配置文件：
sudo nano /etc/samba/smb.conf
最后增加以下内容：
[sharename]
comment = dm film #备注
path = /mnt/dm150G #文件路径
read only = no #是否只读
create mask = 0777 #创建文件及目录权限
directory mask = 0777 #设置访问权限
guest ok = yes #是否允许客人身份访问
browseable = yes #是否浏览权限
重启服务：
sudo samba restart
如果外挂硬盘，设置777权限
在资源管理器访问：
\\ip\sharename
```
## 相关资源
[Mjpg-streamer源程序及官方安装说明](https://github.com/jacksonliam/mjpg-streamer)
[Mjpg-streamer用法说明](https://github.com/jacksonliam/mjpg-streamer/blob/master/mjpg-streamer-experimental/README.md)
[Mjpg-streamer使用讲解](https://www.raspberrypi.org/forums/viewtopic.php?f=43&t=45178)
[关于开机启动很有用的一片文章](https://www.embbnux.com/2015/04/12/raspberry_pi_setting_python_script_start_on_boot/)  
[开机自动执行命令和脚本](https://www.jianshu.com/p/0cd6727aa082)  
[linux开机启动python脚本](https://blog.csdn.net/zj0078/article/details/41926675)  
[linux定时任务执行python脚本](https://www.cnblogs.com/xfvipp/p/7772920.html)  
