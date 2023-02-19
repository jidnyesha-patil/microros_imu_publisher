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


### Micro ROS on Arduino 
https://adityakamath.github.io/2022-06-19-microros-examples/  

Download the latest release for ROS2 Humble as a .zip file (https://github.com/micro-ROS/micro_ros_arduino/releases)   
Add it to the Arduino IDE using the ‘Include library’ option.   
Then, code can be compiled and uploaded in the traditional way on the Arduino IDE.  

### Nano RP2040 on Arduino IDE
https://docs.arduino.cc/tutorials/nano-rp2040-connect/rp2040-imu-basics  

NOTE: Arduino IDE on Linux is unable to upload codes to Nano RP2040 Connect. THe code compiles but when uploading the RP2040 board is disconnected.  
Proposed solution is either using MacOS to upload the code or copying the code file to the RP2040 manually ( Need more data )  

- Install drivers for Nano RP2040 Connect: Tools -> Board -> Board Manager -> Search "Arduino Mbed OS Nano Boards" -> Install  
- Install required library: Tools -> Manage Libraries -> Search "Arduino_LSM6DSOX" -> Install  
- Write code to access accelerometer and gyroscope data  

Resources:  
[1] https://adityakamath.github.io/2022-06-19-microros-examples/  
[2] https://docs.arduino.cc/tutorials/nano-rp2040-connect/rp2040-imu-basics  
      
