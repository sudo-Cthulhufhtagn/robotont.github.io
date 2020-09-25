#####################
Controlling the robot
#####################

   .. image:: /files/pictures/coord.png
      :width: 400

#. The robot driver subscribes to a specific type of messages called *velocity commands*. The standard name for this topic is :code:`/cmd_vel` or :code:`/robotont/cmd_vel` when in robot namespace. 

#. The message is of type :code:`geometry_msgs/Twist` and it's structure can be found from `ROS wiki <https://docs.ros.org/api/geometry_msgs/html/msg/Twist.html>`__.

#. To set and control the robot speed, the velocity commands need to be published continuously.


Setup
------
#. Install teleop twist keyboard

   .. code-block:: bash
      
      sudo apt update
      sudo apt install ros-melodic-teleop-twist-keyboard

#. From your Android device, go to Google Play Store and install the `ROS Control app <https://play.google.com/store/apps/details?id=com.robotca.ControlApp&hl=en>`__.

#. Establish an ssh connection between the robot and the user PC as shown here: :ref:`connecting-remotely`.

Controlling the robot using teleop twist keyboard
-------------------------------------------------

#. Open a new terminal window

#. **On ROBOTONT on-board computer** run the following command:

   .. code-block:: bash
      
         rosrun teleop_twist_keyboard teleop_twist_keyboard.py __ns:=/robotont

   or

   .. code-block:: bash
      
         roslaunch robotont_demos teleop_keyboard.launch

#. Use the following keys to move the robot:

   .. image:: /files/pictures/twist_keys.png
      :width: 400


   .. warning:: From this point beyond, you are able to drive the robot with a keyboard. Should you loose control over the robot, do one of the following
                 
       * PRESS "k" TO STOP THE ROBOT!
       * PRESS THE EMERGENCY SWITCH ON THE ROBOT.
   
   .. hint:: Notice that the teleop node only receives keypresses only when the terminal window is active.
   
   .. tip:: Use :code:`CTRL + C` to stop the node.

Controlling the robot using an Android device
----------------------------------------------
 
#. Open the ROS Control app on your phone

#. Insert the ROBOTONT's IP address into Master URI field by entering the following:

   .. code-block:: bash
      
         http://robotont_IP_address:11311

#. Click on "Show advanced options" in the prompted window and fill in "Joystick" and "Odometry" topic names with "robotont/cmd_vel" and "robotont/odom", respectively

#. Click OK to add the robot

#. Now you can select the robot from the list and teleoperate it using the touch joystick button