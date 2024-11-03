# Gelsight_for_Boundary

Getting Boundaries from gelsight_mini image.

# Overview

This project aims to precisely capture and analyze the posture information of objects grasped by a robotic arm using tactile sensing technology for manipulation purposes.
Utilizing the **GelSight Mini** sensor, our system obtains the directional vectors of objects, and in conjunction with the pose parameters of the **KUKA iiwa14** robotic arm, it accurately computes the actual posture of objects within the world coordinate system. By making real-time adjustments to the end pose of the robotic arm, our system ensures that objects remain perpendicular to the operational plane throughout the process, thereby enhancing operational precision and efficiency.

# Install

After downloading the files, you need to **compile** and **source** tac3d as a ROS2 package. If there are additional dependencies required to run with this package, please adjust the relevant XML files accordingly. Your computer must have a complete **ROS2 Humble** environment installed.

```bash
cd ~/<your_working_layer>
```
```bash
colcon build
```

```bash
source ./install/setup.py
```

Once the entire ROS 2 environment is set up, you can directly invoke the `tac3d` package from the command line by using its package name followed by the name of the specific node or executable you wish to run.

# Get and Publish the oritation

After preparing the robotic arm's gripper equipped with the GelSight Mini sensor, you can activate various nodes to monitor and publish the object's pose.

- Activate the robotic arm pose subscription node (based on `LBR`).
```python3
ros2 run tac3d listener
```

- Activate the node that publishes the object's world coordinates (waiting for GelSight initialization is required).
```python3
ros2 run tac3d orientation_publisher
```

- Activate the pose alignment command publishing node.
```python3
ros2 run tac3d pose_planning_node
```

- We also provide an initial script to help reposition the robotic arm.
```python3
ros2 run tac3d initial
```

# Additional Project References

This section could include information about other projects that may be relevant as references or resources for this project.

- gelsight：
https://github.com/gelsightinc/gsrobotics

- lbr：
https://github.com/lbr-stack/lbr_fri_ros2_stack


