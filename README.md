# Inter-IIT Multi-Robot Gazebo Workspace

[![ROS 2 Humble](https://img.shields.io/badge/ROS_2-Humble-22314E?logo=ros&logoColor=white)](https://docs.ros.org/en/humble/)
[![Gazebo Classic](https://img.shields.io/badge/Gazebo-Classic-FF6F00)](https://classic.gazebosim.org/)

ROS 2 and Gazebo Classic workspace for spawning and experimenting with multiple TurtleBot-style robots, custom worlds, URDF/SDF assets, navigation, SLAM, RViz, and obstacle-detection scripts.

## What is included

- `inter_iit/` - ROS 2 package metadata and CMake configuration
- `launch/` - multi-robot, Gazebo, navigation, localization, SLAM, and RViz launch files
- `config/`, `params/` - robot spawn and Nav2 parameters
- `urdf/`, `models/`, `worlds/` - robot, obstacle, and scene assets
- `scripts/` - obstacle detection, transforms, and shared database helpers
- `rviz/` - visualization configurations

## Requirements and build

Use a compatible ROS 2 Humble/Gazebo Classic environment with `rclpy`, `rclcpp`, `gazebo_ros`, `robot_state_publisher`, Nav2, SLAM Toolbox, RViz, and TurtleBot3 dependencies as required by the selected launch file.

```bash
mkdir -p ~/inter_iit_ws/src
cd ~/inter_iit_ws/src
git clone https://github.com/AjanM27/Inter_IIT.git
cd ..
source /opt/ros/humble/setup.bash
rosdep install --from-paths src --ignore-src -r -y
colcon build --symlink-install
source install/setup.bash
```

## Launch a four-robot scene

The repository includes `launch/spawn_4_bots.launch.py`:

```bash
ros2 launch inter_iit spawn_4_bots.launch.py
```

Other launch files cover localization, navigation, SLAM, RViz, and alternative spawn configurations. Inspect their declared arguments before combining them in a new run.

## Assets and status

The repository includes compressed model archives and several overlapping world/URDF variants. Extract or select only the assets required by the launch file you are using. This is an experimental multi-robot workspace, not a certified autonomy or collision-avoidance system. The package metadata still contains a placeholder license; choose and declare a license before redistribution.
