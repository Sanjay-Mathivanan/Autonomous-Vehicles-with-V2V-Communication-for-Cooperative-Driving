# Launch Scripts (`launch/`)

This directory houses the Python launch files that coordinate ROS2 nodes, read parameter YAML configurations, and compile robot URDF descriptions.

## Script Breakdown

### 1. Main Infrastructure Launches
* [launch_sim.launch.py](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/launch/launch_sim.launch.py): Spawns the robot model inside a Gazebo environment, starts up mapping/navigation parameter servers, controller managers, and joystick teleoperation nodes in simulation.
* [launch_robot.launch.py](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/launch/launch_robot.launch.py): Spawns physical controllers, serial communication handlers to micro-controllers, and the command twist multiplexer on real robot hardware.
* [rsp.launch.py](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/launch/rsp.launch.py): Launches `robot_state_publisher`, evaluating xacro parameters (`sim_mode`, `use_ros2_control`) and publishing TF tree coordinates.

### 2. Navigation & SLAM Mapping Launches
* [online_async_launch.py](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/launch/online_async_launch.py): Starts the asynchronous mapping process via Slam Toolbox.
* [localization_launch.py](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/launch/localization_launch.py): Loads `map_server` and AMCL nodes to localise the robot within a pre-built static map.
* [navigation_launch.py](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/launch/navigation_launch.py): Starts planner, controller, recovery, lifecycle, and behavior tree nodes to guide paths autonomously.

### 3. Actuators, Sensors & Tracking
* [rplidar.launch.py](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/launch/rplidar.launch.py): Runs the RPLiDAR composition node, pointing to serial connection directories.
* [camera.launch.py](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/launch/camera.launch.py): Starts the standard Video4Linux2 camera node (`v4l2_camera_node`).
* [joystick.launch.py](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/launch/joystick.launch.py): Listens to controllers and publishes velocity inputs.
* [ball_tracker.launch.py](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/launch/ball_tracker.launch.py): Runs the color threshold object tracking velocity loops.
