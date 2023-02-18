# microros_imu_publisher
Original - A simple Micro-ROS publisher implementation with ESP-32 dev board &amp; Arduino IDE

## Micro-ROS publisher with Nano RP2040 Connect 

### Micro ROS on Host (Linux) 
#### Create agent
  ##### Download micro-ROS-Agent packages
    ros2 run micro_ros_setup create_agent_ws.sh
  ##### Build step - build packages for agent
  ros2 run micro_ros_setup build_agent.sh
  source install/local_setup.bash
#### Run micro-ROS app
  ##### Run a micro-ROS agent
  ros2 run micro_ros_agent micro_ros_agent udp4 --port 8888
  
  ##### In new terminal, run micro-ROS node
  source /opt/ros/$ROS_DISTRO/setup.bash
  source install/local_setup.bash
  ##### Use RMW Micro XRCE-DDS implementation
  export RMW_IMPLEMENTATION=rmw_microxrcedds
  ##### Run a micro-ROS node
  ros2 run micro_ros_demos_rclc ping_pong


### Micro ROS on Arduino [1]
Download the latest release for ROS2 Humble as a .zip file (https://github.com/micro-ROS/micro_ros_arduino/releases) 
Add it to the Arduino IDE using the ‘Include library’ option. 
Then, code can be compiled and uploaded in the traditional way on the Arduino IDE.

### Nano RP2040 on Arduino IDE


Resources:
[1] https://adityakamath.github.io/2022-06-19-microros-examples/
      
