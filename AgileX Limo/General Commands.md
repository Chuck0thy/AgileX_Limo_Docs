
Start Drive Base
```
ros2 launch limo_base limo_base.launch.py
```

Start Lidar
```
ros2 launch limo_bringup limo_start.launch.py
```

Start Camera
```
ros2 launch orbbec_camera dabai.launch.py
```

Keyboard Drive
```
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```

Lidar Drive
```
ros2 launch limo_bringup limo_nav2.launch.py 
```
## Related Docs

[[Documentation]]
[[Apps]]

###### Agile X Limo