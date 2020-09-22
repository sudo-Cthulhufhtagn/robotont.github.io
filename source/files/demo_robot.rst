#################
Demos on Robotont
#################

Before starting establish an ssh connection between the robot and the user PC as shown here: :ref:`connecting-remotely`.

The following packages are needed to run the demos:

#. For 2D mapping:

   .. code-block:: bash
      
      sudo apt update
      sudo apt install ros-melodic-depthimage-to-laserscan
      sudo apt install ros-melodic-cartographer-ros
      sudo apt install ros-melodic-move-base

#. For 3D mapping:

   .. code-block:: bash
      
      sudo apt install ros-melodic-rtabmap-ros

#. For AR tracking:

   .. code-block:: bash
      
      sudo apt install ros-melodic-ar-track-alvar
 


2D mapping
----------

#. **On Robotont on-board computer** launch 2d_nav_carto.launch

   .. code-block:: bash
      
      roslaunch robotont_demos 2d_nav_carto.launch

#. **On PC** launch display_2d_mapping.launch to visualize the result

   .. code-block:: bash
      
      roslaunch robotont_demos display_2d_mapping.launch

#. To move the robot open another terminal window **on the PC** and run teleop twist keyboard

   .. code-block:: bash
      
      roslaunch robotont_demos teleop_keyboard.launch

   .. hint:: Notice that the teleop node only receives keypresses when the terminal window is active.

3D mapping
----------

#. **On Robotont on-board computer** launch 3d_mapping.launch

   .. code-block:: bash
      
      roslaunch robotont_demos 3d_mapping.launch

#. **On PC** launch display_3d_mapping.launch to visualize the result

   .. code-block:: bash
      
      roslaunch robotont_demos display_3d_mapping.launch

#. To move the robot open another terminal window **on the user PC** and run teleop twist keyboard

   .. code-block:: bash
      
      rosrun teleop_twist_keyboard teleop_twist_keyboard.py __ns:=/robotont

   .. hint:: Notice that the teleop node only receives keypresses when the terminal window is active.

  .. image:: /files/pictures/3dmap.png
    :width: 400

AR tracking
-----------
#. **On Robotont on-board computer** launch ar_follow_the_leader.launch (change tag_nr with your AR tag number)

   .. code-block:: bash
      
      roslaunch roslaunch robotont_demos ar_follow_the_leader.launch marker_id:=tag_nr

#. **On PC** launch display_ar_marker.launch to visualize the result

   .. code-block:: bash
      
      roslaunch robotont_demos display_ar_marker.launch

#. To move the robot open another terminal window **on PC** and run teleop twist keyboard

   .. code-block:: bash
      
      roslaunch robotont_demos teleop_keyboard.launch
    
    
   .. hint:: Notice that the teleop node only receives keypresses when the terminal window is active.

ROS navstack
------------------
#. Using the navstack in ROS is very straightforward, you tell the robot where it is (if it doesnt already know) and where it needs to go.

#. For setting initial pose, click on 2D Pose Estimate and drag the arrow where and how the robot actually is.
 
   .. image:: /files/pictures/poseestimatearrow.png
    :width: 400


#.  To tell the robot where to go, click on 2D Nav Goal
    and drag the arrow to where you want the robot to go
    and which way does it have to face.

   .. image:: /files/pictures/2dnavgoalarrow.png
    :width: 400


#. From *planner.yaml* you can tune the parameters for the planner. Reference can be found `here <http://wiki.ros.org/base_local_planner>`__.
