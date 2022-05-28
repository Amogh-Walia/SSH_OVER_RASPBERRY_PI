# SSH_OVER_RASPBERRY_PI
A small project which aims to control an arduino Board over SSHthrough a Raspberry Pi running ROS. Here in order to demonstrate it, I have Used a Servo

The Project uses Rosserial, a package which contains Arduino-specific extensions required to run rosserial_client on an Arduino. 
It is meant to demonstrate how easy it is to integrate custom hardware and cheap sensors into your ROS project using an Arduino

For this project we first setup a raspberry Pi running Ubuntu Noetic and ROS, and added headerless SSH Access.

After this, we installed and configured Rosserial on both the terminal machine and the raspberry Pi.



Finally to use the demo file, we created a simple Servo controlling arduino sketch.

To run the project, we use the following commands

Roscore <To start up ROS >
  
rosrun rosserial_python serial_node.py /dev/ttyACM0 <To start the rosserial instance at the COM PORT connected to the arduino>
  
 and finally
 
  rostopic pub servo std_msgs/UInt16  180 <Which publishes the input value  to the arduino board>
 
All the above commands are given over the SSH Link established and hence serve as a proof of concept of how further projects can be made using this .
  
  
  Demonstration:- https://drive.google.com/file/d/1u9KtiBqCjQrypj0XfLPdblhQjejUoF_Y/view?usp=drivesdk
