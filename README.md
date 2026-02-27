# ROS 2 Examples

My personal ROS 2 practice repository.

## Structure

```text
ros2_examples/
├── README.md
└── ros2_ws/
    └── src/        # ROS 2 packages
```

## Create First ROS 2 Package

```bash
cd ros2_ws/src
ros2 pkg create --build-type ament_python my_first_pkg

cd ..
colcon build --symlink-install
source install/setup.bash
```

## Resulting Workspace Layout

```text
ros2_examples/
├── .gitignore
├── README.md
└── ros2_ws/
    ├── src/        # ROS 2 packages
    ├── build/      # Ignored by Git
    ├── install/    # Ignored by Git
    └── log/        # Ignored by Git
```

## Required `~/.bashrc` Configuration

Add this to the end of `~/.bashrc`:

### ROS 2 Jazzy

```bash
source /opt/ros/jazzy/setup.bash
```

### ROS 2 Workspace Overlay

```bash
if [ -f ~/Documents/ros2_examples/ros2_ws/install/setup.bash ]; then
    source ~/Documents/ros2_examples/ros2_ws/install/setup.bash
fi
```

## Daily Workflow

```bash
ssh orangepi
cd ~/Documents
```

If the repository is not cloned:

```bash
git clone https://github.com/loolcodez/ros2_examples
```

Build and run:

```bash
cd ros2_examples/ros2_ws
colcon build
source install/setup.bash
ros2 run my_pkg my_node
```

## Notes

- Always source `/opt/ros/jazzy` before your workspace.
- Use `--symlink-install` during development.
- Never commit `build/`, `install/`, or `log/`.
