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
colcon build --symlink-install
source install/setup.bash

# Result should be like this
ros2_examples/
├── .gitignore
├── README.md
└── ros2_ws/
    ├── src/        # ROS2 packages
    ├── build/      # Ignored by Git
    ├── install/    # Ignored by Git
    └── log/        # Ignored by Git

# Required ~/.bashrc Configuration
Add this end of ~/.bashrc:

# ROS 2 Jazzy
source /opt/ros/jazzy/setup.bash

# ROS 2 workspace overlay
if [ -f ~/Documents/ros2_examples/ros2_ws/install/setup.bash ]; then
    source ~/Documents/ros2_examples/ros2_ws/install/setup.bash
fi

# Daily workflow
ssh orangepi
cd ~/Documents

If repository is not cloned:
git clone https://github.com/loolcodez/ros2_examples

Build and run:
cd ros2_examples/ros2_ws
colcon build
source install/setup.bash
ros2 run my_pkg my_node

Notes
- Always source /opt/ros/jazzy before your workspace.
- Use --symlink-install during development.
- Never commit build/, install/, or log/.
