aubo_i10_ros_melodic
============================
安装前提：使用小鱼一键安装了 ros melodic 和 rosdepc

一键安装指令：
```
wget http://fishros.com/install -O fishros && . fishros
```
---
一、aubo package安装

1.创建文件夹  
```mkdir -p ~/aubo_ws/src```

2.进入src目录   
```cd ~/aubo_ws/src/```

3.下载ros package  
```git clone https://github.com/dashuaip/HUST_aubo_ros_melodic.git ```

或  

```git clone https://gitee.com/dashuaip/HUST_aubo_ros_melodic.git```

4.安装依赖  
```sudo apt install ros-melodic-industrial-*```

5.安装依赖  
```sudo apt install ros-melodic-rviz-*```

6.安装依赖  
```sudo apt install ros-melodic-gazebo-*```

7.安装依赖  
```sudo apt install ros-melodic-moveit-*```

8.创建软链接  
```sudo ln -sf /usr/include/eigen3/Eigen/ /usr/include/Eigen```

9.创建软链接  
```sudo ln -sf /usr/include/eigen3/unsupported/ /usr/include/unsupported```

10.下载依赖库   
```wget http://archive.ubuntu.com/ubuntu/pool/main/p/protobuf/libprotobuf9v5_2.6.1-1.3_amd64.deb```

11.安装依赖库   
```sudo dpkg -i libprotobuf9v5_2.6.1-1.3_amd64.deb```

12.安装依赖   
```rosdepc install -y --from-paths . --ignore-src --rosdistro melodic -r```

13.回到工作空间目录  
```cd ~/aubo_ws```

14.编译  
```catkin_make```

或  

```catkin build```

15.注意***处修改成自己的用户名   
```echo "source /home/***/aubo_ws/devel/setup.bash" >> ~/.bashrc```

---
二、aubo robot运行

1.rviz  
```roslaunch aubo_i10_moveit_config moveit_planning_execution.launch robot_ip:=127.0.0.1```

2.gazebo  
使用之前先修复这个错误：https://blog.csdn.net/weixin_42237861/article/details/123975426?spm=1001.2014.3001.5502  
```roslaunch aubo_gazebo aubo_i10_gazebo_control.launch```
