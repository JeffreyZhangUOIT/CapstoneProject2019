# CapstoneProject2019
FAQ written by Jeffrey Zhang

Q: What am I looking at?
A: This is the full simulation package for the 8x8 scaled electric combat vehicle (SECV). The folder titled "bot_2dnav" contains files for running the navigation stack. By default we are using an amcl demo, mapped to the 3rd floor sirc. 

The folder "bot_description" contains the files that configure controllers, describe the robot, and launch the simulation.
The folder "bot_interface" is a simple c++ program that helps with remapping the /cmd_vel topic to /bot/bot_velocity_controller/cmd_vel and /bot/joint_states to /bot/bot_velocity_controller/joint_states
The folder "ros_controllers" contains many different controllers that a robot can be configured to use in Gazebo.
The folder "gazebo_ros_pkgs" is necessary for the bot_interface to operate correctly, since msg libraries are being utilized.

Q: Why do I need gazebo 7 and ROS indigo?
A: Somehow due to a miscommunication, the project was worked on ROS kinietic kame while it was neccessary for it to be done in ROS indigo igloo. I blame Aaron Tan. Also, the model of the SIRC 3rd floor map is created using STL version 1.6, which is not compatible with Gazebo 2. Re-creating the map of the SIRC 3rd floor in STL 1.4 should theoretically eliminate the need for Gazebo 7.

Q: How do I change the robot?
A: Inside of the bot_description folder should be a file called "bot.urdf.xacro". Loading this file into your typical text editor will allow you to change most if not all of the robot model's details. For example, if you wanted to change the mesh so that the simulation will run faster, you could change the line: 
<mesh filename="package://bot_description/meshes/TrueECV.dae"/>  to 
<mesh filename="package://bot_description/meshes/carfullblended.dae"/> 

Q: How do I configure the navigation stack?
A: Inside of the bot_2dnav folder contains another folder called params. Those .yaml files can be modified to change move_base.
There is also a file at: /bot_2dnav/launch/amcl_demo.launch. This file can be modified to change amcl behavior.

Q: Why does gazebo/ros/anything crash so frequently when launching?
A: I wish I knew. ROS is a distributed system, so I blame that.

Q: Can ROS operate in real time?
A: No, at the time of writing this FAQ. April 10, 2019.

Q: Who do I contact if I need help with these files?
A: You can contact Jeffrey Zhang via email: "jeffrey.zhang@uoit.net". Whether you get a response or not is up to chance, and if that particular email still works. Contacting any of the other group members for this capstone project is useless, since they know nothing.

Q: Do they really know nothing?
A: No, not nothing. As far as the actual work of the capston project is involved, Nicolas Zarfino created the mesh of the model. Navjot Aulakh added the lidar scanner to the URDF and played around with configuring the navigation stack. So basically nothing.

Q: Are you salty Jeffrey?
A: Yeah, a bit. However, I think that if anyone reads this far into an FAQ, they deserve to know the truth of this project. Who knows, maybe someone will be impressed that I did the work of a capstone project for 4 people by myself?
