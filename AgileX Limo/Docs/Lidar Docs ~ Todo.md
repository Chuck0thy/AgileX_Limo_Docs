YDLIDAR T-mini Pro lidar is a 360° 2D lidar (hereinafter referred to as T-mini Pro) developed by Shenzhen EAI Technology Co., Ltd.
###### Specs
![[Lidar_Specs.png]]

## Start-up
>**Note:** Because ros1 and ros2 are both installed, each time you open a new terminal, please choose 2(ros2)

**Open a new terminal and input 2. Then click enter.**
Launch a new terminal and enter the command:
```
ros2 launch limo_bringup limo_start.launch.py
```

After launching successfully, the terminal will output the following log information, as shown in the figure:

![[Lidar_Log.png]]

Then launch a new terminal and enter the command in the terminal:
```
rviz2
```

After the rviz visualization software runs successfully, the rainbow data displayed is the laser data scanned by LiDAR.

![[Lidar_Rviz.png]]

At this time, you can set the remote control/App to remote control mode and the remote control car will move. The laser data will also change accordingly.

## Mapping
###### Intro
Cartographer is a set of SLAM algorithms based on image optimization launched by Google. The main goal of this algorithm is to achieve low computing resource consumption and achieve the purpose of real-time SLAM. The algorithm is mainly divided into two parts. The first part is called Local SLAM. This part establishes and maintains a series of Submaps through each frame of the Laser Scan, and the so-called submap is a series of Grid Maps. The second part called Global SLAM, is to perform closed-loop detection through Loop Closure to eliminate accumulated errors: when a submap is built, no new laser scans will be inserted into the submap. The algorithm will add the submap to the closed-loop detection.

###### Operation
> **Note:** Before running the command, please make sure that the programs in other terminals have been terminated. The termination command is: Ctrl+c.

> **Note:** The speed of limo should be slow  in the process of mapping. If the speed is too fast, the effect of mapping will be affected.

Start-up the Lidar by launching a new terminal and entering the command:
```
ros2 launch limo_bringup limo_start.launch.py
```

Then start the cartographer mapping algorithm. Open another new terminal and enter the command:
```
ros2 launch limo_bringup cartographer.launch.py 
```

After launching successfully, the rviz visualization interface will be shown in the figure below:
![[Lidar_Cartographer.png]]

After scanning the desired space, the map should be saved.

（1）Enter the map saving directory.

```
cd /home/agilex/limo_ros2_ws/src/limo_ros2/limo_bringup/maps
```

（2）Enter the following command in terminal.

```
ros2 run nav2_map_server map_saver_cli -f map11
```

