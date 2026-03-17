The myCobot 280 series of robotic arms are 6-DOF collaborative robots developed by Elephant Robotics specifically for research and education, science and technology applications, and commercial exhibitions. The AgileX Limo uses the 280 M5.

## Setup
To start the robotic arm. If you see the interface below, please configure the robotic arm communication. Choose 'Transponder', click 'ok'.
![[Arm_Menu_Main.png]]

Then choose 'USB UART' and click ok.
![[Arm_Menu_Transponder.png]]

Finally, 'Atom: ok' shows successful configuration.
![[Arm_Menu_USB.png]]

Now leave it on that screen, then run this command:
```
ls /dev/ttyACM*
```
This is to see if there is a USB ACM device (usually ACM0)

Then run,
```
sudo chmod 777 /dev/ttyACM*
```
To grant permissions.

>**Note:** If any errors occur during the following steps, you can refer to this [link](https://github.com/smalleha/mycobot_ros2_agx.git) to update the code.

## Use
### Slider Control of Simulated Robotic Arm
> Note: Make sure the robotic arm is connected before starting

Start the slider control node. Open a new terminal, and enter the command in the terminal:

```
ros2 launch mycobot_280 slider_control.launch.py port:=/dev/ttyACM0 baud:=115200
```
![[Arm_Control_Sim.png]]

Control the movement of the robotic arm by dragging the slider.

### Rviz Model Follow
> Note: Make sure the robotic arm is connected before starting

Start the model following node:

```
ros2 launch mycobot_280 mycobot_follow.launch.py 
```

If the above command fails, please run the following command to set the port name and baud rate:

```
 ros2 launch mycobot_280 mycobot_follow.launch.py port:=/dev/ttyACM0 baud:=115200
```

After successful startup, the robotic arm will be unlocked. At this time, the robotic arm can be moved by hand, and the model in rviz will also move accordingly.
![[Arm_Control_Follow.png]]
### GUI Control
> Note: Make sure the robotic arm is connected before starting.

Use a simple GUI interface to control the movement of the robotic arm. Start a new terminal and enter the command after the terminal:

```
ros2 launch mycobot_280 simple_gui.launch.py
```

If the above command fails, please run the following command to set the port name and baud rate:

```
ros2 launch mycobot_280 simple_gui.launch.py port:=/dev/ttyACM0 baud:=115200
```

After successful launching, the angle information or position information of each joint can be entered in the GUI interface.
![[Arm_Control_GUI.png]]

## Related
> For Troubleshooting please refer to [[Arm Troubleshooting]]

[[Debug GUI]]