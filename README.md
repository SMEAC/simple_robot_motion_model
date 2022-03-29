# simple_robot_motion_model

This ROS package provides a slight step back from the simple_robot_custom_ctlr model, by removing the world files, but adding a gazebo plug in to provide the ground truth position of the robot.  It allows parameters to be recorded from its movement for development of a motion model.

Included in the package are:
* Package.xml and CMakeLists.txt files
* a xacro and gazebo file, enhanced slightly from the simple_robot package to include different colors for each wheel, in order to allow easier debugging from RVIZ.  Additionally the appropriate velocity controllers are appied inside the gazebo file.
* a config file for the velocity controllers
* a launch file for Gazebo and Rviz
* a config file for Rviz

To test the Package, start the launch file, see that no errors appear in the command window while starting Gazebo and then in a second terminal window, send a command to one of the velocity controllers with:

rostopic pub wheel_left_velocity_controller/command std_msgs/Float64 -- '20'

or 

rostopic pub wheel_right_velocity_controller/command std_msgs/Float64 -- '20'
