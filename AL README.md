last updated, 21/01/19

# ur_modern_driver

A new driver for the UR3/UR5/UR10 robot arms from Universal Robots. It is designed to replace the old driver transparently, while solving some issues, improving usability as well as enabling compatibility  of ros_control. 

## A.Luu Modifications from Original ur_modern_driver.

See README.md document for original ur_modern_driver documentation. 

To connect to the UR10, the original command was:
```roslaunch ur_modern_driver ur10_bringup.launch robot_ip:=<VALUE>```
'
This has now been extended to include custom URDF and SRDF configurations for the UR10 robot. 

Now, to connect to the UR10, the new roslaunch command is:
```roslaunch ur_modern_driver custom_ur10_bringup.launch robot_ip:=<VALUE> robot_name:=<VALUE> user:=<VALUE>```

Whereby, robot_name can include *mod_ur10, ftdrill_ur10, full_robotiq_ur10* the differences between is explained in ~/robot_trajectory/README.md. 
The user argument is simply the user's name as relative paths were not configured for this launch file. 

To check your username, open a new terminal ```ctrl+T``` and type ```pwd```. The result should look something like ```/home/mia/designrobotics...```. In this case, "mia" is the username and is input as an argument for the roslaunch command.

A complete example command would be: 

```roslaunch ur_modern_driver custom_ur10_bringup.launch robot_ip:=192.168.0.1 robot_name:=ftdrill_ur10 user:=mia```