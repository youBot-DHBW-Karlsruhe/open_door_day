# Open-Door Day
YouBot-Demonstration für den Tag der offenen Tür

## ROS-Master starten
`roscore`

## Youbot Treiber
`roslaunch youbot_driver_ros_interface youbot_driver.launch`

## Fernsteuer-App
`rosrun youbot_driver_ros_interface youbot_keyboard_teleop.py`

## Beispiel-Befehle

### Arm
#### Ausfahren:

`rostopic pub /arm_1/arm_controller/position_command brics_actuator/JointPositions '{positions:[ {joint_uri: arm_joint_1, unit: rad, value: 2.95}, 
{joint_uri: arm_joint_2, unit: rad, value: 1.05}, 
{joint_uri: arm_joint_3, unit: rad, value: -2.44}, 
{joint_uri: arm_joint_4, unit: rad, value: 1.73}, 
{joint_uri: arm_joint_5, unit: rad, value: 2.95}]}'`

#### Einfahren:

`rostopic pub /arm_1/arm_controller/position_command brics_actuator/JointPositions '{positions:[ {joint_uri: arm_joint_1, unit: rad, value: 0.11}, 
{joint_uri: arm_joint_2, unit: rad, value: 0.11}, 
{joint_uri: arm_joint_3, unit: rad, value: -0.11}, 
{joint_uri: arm_joint_4, unit: rad, value: 0.11}, 
{joint_uri: arm_joint_5, unit: rad, value: 0.111}]}'`

### Gripper:

#### Loslassen
`rostopic pub /arm_1/gripper_controller/position_command brics_actuator/JointPositions '{positions:[ {joint_uri: gripper_finger_joint_l, unit: m, value: 0.0115},
{joint_uri: gripper_finger_joint_r, unit: m, value: 0.0115}]}'`

#### Greifen
`rostopic pub /arm_1/gripper_controller/position_command brics_actuator/JointPositions '{positions:[ {joint_uri: gripper_finger_joint_l, unit: m, value: 0},
{joint_uri: gripper_finger_joint_r, unit: m, value: 0}]}'`
