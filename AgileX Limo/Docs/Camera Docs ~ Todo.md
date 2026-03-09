ORBBEC®Dabai is a depth camera based on binocular structured light 3D imaging technology.
## Use
First start the camera by running this command
```
ros2 launch orbbec_camera dabai.launch.py
```

The following warnings will appear during running. This is because some parameters in the driver are not supported by the camera and can be ignored.

![[Camera_Errors.png]]
### View Camera Info
Open RViz in new terminal
```
rviz2
```

Set fixed frame to "camera_link"

![[Camera_Fixed_Frame.png]]

Click add and add the PointCloud2 component to view point cloud data

![[Camera_PointCloud.png]]

Set the PointCloud2 topic to "/camera/depth/points"

![[Camera_PointCloud_Topic.png]]

