# ROS2 Examples

My personal ROS2 practice repository.

## Structure

ros2_examples/
- ros2_ws/ → ROS2 workspace
- src/ → packages


# Create first ROS2 package
cd ros2_ws/src
ros2 pkg create --build-type ament_python my_first_pkg

cd ..
colcon build
source install/setup.bash

# Result should be like this
ros2_examples/
├── .gitignore
├── README.md
└── ros2_ws/
    ├── src/
    ├── build/      (Git ignored)
    ├── install/    (Git ignored)
    └── log/        (Git ignored)

