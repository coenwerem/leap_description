# ROS2 Leap Hand Description Package
 
ROS2 package for launching and visualizing the urdf of the leap hand grippers. Only works for the right hand currently, but I hope to add components for the left hand soon. 

## Dependencies
This README assumes that you have the following ROS2 installation setup:

    - Ubuntu Distro="jammy"
    - ROS Distro="humble"

## Installation
To install this package, perform the following steps:
- Clone the repo in your ROS2 workspace folder.
- Run `rosdep install --from-paths src --ignore-src -r -y --rosdistro=humble`
- Run `colcon build` (append `--packages-select leap_description` to your build command if you want to build just this package).
- Source your workspace and ROS2 installation.
- Run `ros2 launch leap_description view_gripper.launch.py`

You should see the following windows pop up if everything works as it should:

|          |         |
| -------- | ------- |
|![Center Grasp Pose](docs/center_grasp_pose.png) | ![Joint State Publisher](docs/joint_state_publisher_leap_hand.png)|
| Center Grasp Pose on RViZ   | Joint State Publisher GUI |
|          |         |

## Credits
The URDF files for the Leap Hand were obtained from the excellent [`dex-urdf`](https://github.com/dexsuite/dex-urdf) repo, while the description launch and rviz files have been created by adapting corresponding files in the Robotiq gripper description package provided by [PickNik Robotics](https://github.com/PickNikRobotics/ros2_robotiq_gripper).