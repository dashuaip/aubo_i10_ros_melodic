前提：使用小鱼一键安装了 ros melodic 和 rosdepc

一键安装指令:wget http://fishros.com/install -O fishros && . fishros

aubo安装
1.mkdir -p ~/aubo_ws/src

2.cd ~/aubo_ws/src/

3.git clone https://github.com/dashuaip/HUST_aubo_ros_melodic.git 
(或 git clone https://mirror.ghproxy.com/https://github.com/dashuaip/HUST_aubo_ros_melodic.git)

4.sudo apt install ros-melodic-industrial-*

5.sudo apt install ros-melodic-rviz-*

6.sudo apt install ros-melodic-gazebo-*

7.sudo apt install ros-melodic-moveit-*

8.sudo ln -sf /usr/include/eigen3/Eigen/ /usr/include/Eigen

9.sudo ln -sf /usr/include/eigen3/unsupported/ /usr/include/unsupported

10.wget http://archive.ubuntu.com/ubuntu/pool/main/p/protobuf/libprotobuf9v5_2.6.1-1.3_amd64.deb

11.sudo dpkg -i libprotobuf9v5_2.6.1-1.3_amd64.deb

12.rosdepc install -y --from-paths . --ignore-src --rosdistro melodic -r

13.cd ~/aubo_ws

14.catkin_make

15.echo "source /home/r/aubo_ws/devel/setup.bash" >> ~/.bashrc

16.chmod +x aubo_ws/src/HUST_aubo_ros_melodic/aubo_controller/script/aubo_controller/aubo_robot_simulator 

aubo运行
1.roslaunch aubo_i10_moveit_config moveit_planning_execution.launch robot_ip:=127.0.0.1

2.roslaunch aubo_gazebo aubo_i10_gazebo_control.launch 
