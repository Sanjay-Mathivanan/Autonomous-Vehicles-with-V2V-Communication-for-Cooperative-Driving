# Robot URDF/Xacro Descriptions (`description/`)

This directory contains the files defining the robot's physical visual structures, collision hulls, joint dynamics, simulated hardware sensors, and controller plugin configurations.

## File Breakdown

### 1. Core Model
* [robot.urdf.xacro](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/description/robot.urdf.xacro): The top-level entrypoint that stitches all helper sub-files together based on flags (e.g. `use_ros2_control`).
* [robot_core.xacro](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/description/robot_core.xacro): Declares base link offsets, chassis links, continuous left/right wheel joints, and the low-friction caster wheel.
* [inertial_macros.xacro](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/description/inertial_macros.xacro): Mathematical xacro macros used to easily define inertia tensors for cylinders, boxes, and spheres based on mass and size variables.

### 2. Actuation Control Plugins
* [ros2_control.xacro](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/description/ros2_control.xacro): Configures the controllers. Spawns `gazebo_ros2_control` in simulation, or redirects to `diffdrive_arduino/DiffDriveArduino` connecting via serial `/dev/ttyUSB0` on physical robot hardware.
* [gazebo_control.xacro](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/description/gazebo_control.xacro): Legacy open-loop Gazebo diff-drive plugin used when ROS2 Control is bypassed.

### 3. Integrated Sensors
* [lidar.xacro](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/description/lidar.xacro): Mounts a LiDAR scanner visual geometry and binds it to the `libgazebo_ros_ray_sensor.so` plugin publishing `/scan`.
* [camera.xacro](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/description/camera.xacro): Standard monocular camera model backed by `libgazebo_ros_camera.so` publishing `/camera/image_raw`.
* [depth_camera.xacro](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/description/depth_camera.xacro): Alternative depth camera sensor configuration (commented out by default).

### 4. Custom Aesthetics
* [face.xacro](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/description/face.xacro): Visual elements defining face components (eyes, mouth/nose) mounted on the front of the chassis block to aid orientation verification in Gazebo.
