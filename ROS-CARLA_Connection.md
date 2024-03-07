# Connecting ROS and CARLA

ROS Bridge, officially supported by the CARLA simulator, is a ROS package that allows bidirectional communication between ROS and CARLA. 
Information coming from the CARLA simulator server is converted into topics and, similarly, topics issued between nodes in ROS are converted into commands available in CARLA. Both ROS1 and ROS2 are available, and have the following features.

1. Sensor data provided by: LIDAR, Semantic LIDAR, Cameras (depth, segmentation, rgb, dvs), GNSS, Radar, and IMU.
2. Provide traffic data: transformations, traffic light status, display markers, collision, lane invasion.
3. Steering, accelerator and brake to control AD agents.
4. CARLA simulation control: synchronous mode, simulation playback and pause, and simulation parameter adjustment.


