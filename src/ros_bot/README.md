# ros_bot (ROS2 Package)

This folder contains the core ROS2 package for the `ros_bot` platform, implementing robot description components, configuration files, and launch files for both simulation and physical deployments.

## Package Structure
* **`config/`**: Configuration parameter files for Navigation2 (Nav2), Slam Toolbox (mapping), controllers (`gazebo_ros2_control` and real Arduino parameters), joystick teleop, and `twist_mux` command multiplexer.
* **`description/`**: URDF robot model files defined in Xacro format:
  * `robot.urdf.xacro`: Main URDF entrypoint.
  * `robot_core.xacro`: Basic links and joints (chassis, wheels, caster wheel).
  * `gazebo_control.xacro` / `ros2_control.xacro`: Gazebo/Arduino driver controller plugins.
  * `lidar.xacro` / `camera.xacro`: Simulated laser scan and camera interfaces.
  * `face.xacro`: Visual components for robot front face indicators.
* **`launch/`**: Python launch scripts managing nodes for simulation, mapping, path planning, and physical hardware connections.
* **`worlds/`**: Gazebo Classic XML world definition files containing various mock environments and obstacle courses.

## Documentation Reference
For full installation guidelines, detailed system architecture diagrams, and run commands, please refer to the main project documentation:
👉 **[Main Project README.md](../../README.md)** at the root of the workspace.
