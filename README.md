# ps4_ros
Sony PlayStation 4 DualShock®4 node joy_msg to twist_msg. The connection with Sony PlayStation 4 DualShock®4 is established using Bluetooth.

# Installation
1. Install __ds4dr__: `$sudo pip install ds4drv`
1. Install __ros-joy__: http://wiki.ros.org/joy
1. Go into pairing mode with PS4: Playstation button + share button for ~5 sec
1. Run `sudo ds4drv` from command line to connect to PS4
  1. This will output something like _Created devices /dev/input/jsX
  1. remember /dev/input/js__X__ and update the launch file (default X=0)
  1. `$ sudo chmod a+rw /dev/input/jsX`

# Starting
1. Go into pairing mode with PS4 controller: Playstation button + share button until withe led starts flashing.
2. `sudo ds4drv` if it is not running already.
3. `$ roslaunch ps4_ros ps4`

## Arguments
- `device_name`: name assigned to the device. It is the joystick name appearing when launching `sudo ds4drv`
- `pub_topic_twist`: name of the topic where the PS4 controller publishes twist messages
- `max_linear_twist`: max linear twist
- `max_angular_twist`: max angular twist

# Troubleshooting

* Display raw _ds4drv_ data
  * `$sudo jstest /dev/input/jsX`
  

# Reference
- Adapted from [PS4-ros](https://github.com/solbach/ps4-ros)
