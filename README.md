# TB3基于Web的视频监控
![image](https://github.com/sun-coke/web_video/blob/master/Scr.png)

### A、安装

#### 1. 安装rosbridge-suite，web_video_server

```
$ sudo apt-get install ros-kinetic-rosbridge-suite
$ sudo apt-get install ros-kinetic-web-video-server
```

### B、配置

#### 1. 因为IP的地址要配置很多个地方，所以，写到/etc/hosts里面

```shell
# 查看ip地址和用户名
$ ifconfig #得到IP地址
$ hostname # 得到主机名
$ vim /etc/hosts # 在里面添加 IP[tab]Hostname
```
### C、运行

#### 1.由于视频传输地址默认端口号为8080，这里监控原始图像信息/camera/rgb/image_raw
```
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch 
$ roslaunch rosbridge_server rosbridge_websocket.launch
$ rosrun web_video_server web_video_server
```
#### 2.网页端输入如下网址：
http://localhost:8080/stream?topic=/camera/rgb/image_raw
