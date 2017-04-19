Launch files for Pioneer P3DX and SICK laser.


#1. PREREQUISITE

Following packages are needed befor launching the launch files in this package:

	joy
	rosaria
	ps3_robot_controller
	sick_tool_box
	map_server
	amcl
	move_base

### 1.1 joy
See [configure a linux joystick][1] for details on how to install joy package

### 1.2 rosaria and ps3_robot_controller
The rosaria and ps3_robot_controller packages are already in this workspace. So you can install them just by running catkin build command:

`catkin_make`

You may need to use rosdep to automatically install the ARIA dependency before installing rosaria with following commands:

`rosdep update`

`rosdep install rosaria`

### 1.3 sick tool box
SICK tool box is the driver of SICK laser. You can install it by typing the following command in terminal:

`sudo apt-get install ros-indigo-sicktoolbox-wrapper`

### 1.4 map server
`sudo apt-get install ros-indigo-map-server`

### 1.5 amcl
`sudo apt-get install ros-indigo-amcl`

### 1.6 move_base
`sudo apt-get install ros-indigo-move-base`


#2. USAGES OF LAUNCH FILES

### 2.1 ps3_controller.launch
Used to control robot with ps3 controller. And run ARIA, to connect the robot

### 2.2 mapping.launch
Used to do gmapping, i.e., build maps

### 2.3 pioneer_nav.launch
Used to do navigation


#3. ABOUT CONTROLLER
The left four direction buttons control the robot moving forward and backward and rotating. In the right part of the controller, the right button(PS3_BUTTON_ACTION_CIRCLE) is emergency stop button; the top button(PS3_BUTTON_ACTION_TRIANGLE) enables the motors after emergency stop

#4. OTHER 

If you are going to use ps3 controller for sequrity consideration, you should run the following command to 
connect the wireless ps3 joystick with the computer after launching ps3_controller.launch:

`rosrun ps3joy ps3joy.py`

See [Pair the PS3 Joystick with a Bluetooth Dongle][2] for details on how to pair the ps3 joystick with the computer

[1]: http://wiki.ros.org/joy/Tutorials/ConfiguringALinuxJoystick

[2]: http://wiki.ros.org/ps3joy/Tutorials/PairingJoystickAndBluetoothDongle

