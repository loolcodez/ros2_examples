# Hello World example

## Source
https://github.com/YahboomTechnology/ROS-robot-expansion-board/blob/main/5.ROS2%20basic%20course/6.ROS2%20node.pdf

## Create Python package
```bash
cd ros2_ws/src
ros2 pkg create pkg_helloworld_py --build-type ament_python --dependencies 'rclpy' --node-name 'helloworld'
```
## Write code

# Build package
```bash
cd ..
colcon build --packages-select pkg_helloworld_py --symlink-install
```

## Fresh the environment variables
```bash
source install/setup.bash
```

## Run the node
```bash
ros2 run pkg_helloworld_py helloworld
```