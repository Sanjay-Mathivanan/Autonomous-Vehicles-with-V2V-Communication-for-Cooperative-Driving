# Configuration Parameters (`config/`)

This directory contains the parameter configurations (`.yaml`) and RViz visualization layouts (`.rviz`) used to set up controllers, sensors, navigation, and visualization profiles.

## File Breakdown

### 1. Controllers & Multiplexers
* [my_controllers.yaml](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/config/my_controllers.yaml): Configures `diff_drive_controller` (wheel radius, separation, joints, frames, limits) and `joint_state_broadcaster` for the ROS2 Control framework.
* [twist_mux.yaml](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/config/twist_mux.yaml): Multiplexes command velocities, prioritizing manual joystick input (`cmd_vel_joy` @ priority 100) over vision tracker commands (`cmd_vel_tracker` @ priority 20) and autonomous navigation (`cmd_vel` @ priority 10).

### 2. Navigation & SLAM Mapping
* [nav2_params.yaml](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/config/nav2_params.yaml): Parameters for the Navigation2 stack, including costmap settings, trajectory planners, recovering behavior trees, and controller servers.
* [mapper_params_online_async.yaml](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/config/mapper_params_online_async.yaml): Settings for `slam_toolbox` asynchronous online mapping (resolutions, loops, updates, and thresholds).

### 3. Simulation & Joystick Parameters
* [gazebo_params.yaml](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/config/gazebo_params.yaml) & [gaz_ros2_ctl_use_sim.yaml](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/config/gaz_ros2_ctl_use_sim.yaml): Configures the Gazebo classic sim engine parameter sets and force sim-time flags.
* [joystick.yaml](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/config/joystick.yaml): Maps raw joystick axes and buttons to drive velocities and speed multipliers.

### 4. RViz Visualization Profiles
* [main.rviz](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/config/main.rviz) / [map.rviz](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/config/map.rviz): Layouts showing global costmaps, occupancy grids, planned paths, and laser scans.
* [view_bot.rviz](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/config/view_bot.rviz) / [drive_bot.rviz](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/config/drive_bot.rviz): Simpler layouts geared toward model structural verification and teleoperation telemetry.
