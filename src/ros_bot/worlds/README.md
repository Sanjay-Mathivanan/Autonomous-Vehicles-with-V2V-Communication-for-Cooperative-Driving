# Gazebo Simulation Worlds (`worlds/`)

This directory houses the world environment definitions (`.world` XML files) used in Gazebo Classic simulation runs to test SLAM mapping, obstacle detection, and navigation path planners.

## File Breakdown

* [empty.world](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/worlds/empty.world): A baseline minimal simulation environment containing only a flat ground plane and a light source. Ideal for basic kinematics testing, open-loop velocity checks, and telemetry sanity validations.
* [obstacles.world](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/worlds/obstacles.world): An indoor labyrinth layout containing a series of walls, static obstacles, pillars, cardboard boxes, and spheres. Useful for mapping complex spaces and verifying Nav2 dynamic inflation layers and recovery behaviors.
* [new.world](file:///d:/New%20folder/PROJECTS/Autonomous-Vehicles-with-V2V-Communication-for-Cooperative-Driving-main/src/ros_bot/worlds/new.world): An alternative customized obstacle configuration world.
