.. _demos_on_robot:

#################
Demos on Robotont
#################

Before using the demos see: :ref:`before_starting`.

Note that some of the commands will run on Robotont on-board computer and some on user PC.

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

Uses Cartographer to create a 2D map of the robot's surroundings.

#. **On Robotont on-board computer or on PC** launch 2d_slam.launch

   .. code-block:: bash
      
      roslaunch robotont_demos 2d_slam.launch

#. **On PC** launch 2d_slam_display.launch to visualize the result

   .. code-block:: bash
      
      roslaunch robotont_demos 2d_slam_display.launch

#. To move the robot open another terminal window **on robotont on-board computer or on the PC** and run teleop twist keyboard

   .. code-block:: bash
      
      roslaunch robotont_demos teleop_keyboard.launch

   .. hint:: Notice that the teleop node only receives keypresses when the terminal window is active.

Setting 2D navigation goals
****************************

#. Using the navstack in ROS is very straightforward, you tell the robot where it is (if it doesnt already know) and where it needs to go.

#. For setting initial pose, click on 2D Pose Estimate and drag the arrow where and how the robot actually is.
 
   .. image:: /files/pictures/poseestimatearrow.png
    :width: 400


#.  To tell the robot where to go, click on 2D Nav Goal
    and drag the arrow to where you want the robot to go
    and which way does it have to face.

   .. image:: /files/pictures/2dnavgoalarrow.png
    :width: 400


3D mapping
----------

Creates a 3D map of the robot's surroundings.

#. **On Robotont on-board computer or on PC** launch 3d_mapping.launch

   .. code-block:: bash
      
      roslaunch robotont_demos 3d_mapping.launch

#. **On PC** launch 3d_mapping_display.launch to visualize the result

   .. code-block:: bash
      
      roslaunch robotont_demos 3d_mapping_display.launch

#. To move the robot open another terminal window **on robotont on-board computer or on user PC** and run teleop twist keyboard

   .. code-block:: bash
      
      rosrun robotont_demos teleop_keyboard.launch

   .. hint:: Notice that the teleop node only receives keypresses when the terminal window is active.

  .. image:: /files/pictures/3dmap.png
    :width: 400

AR tracking
-----------

The robot identifies and tracks the pose of the provided AR tag and acts accordingly.

#. **On Robotont on-board computer or on PC** launch ar_follow_the_leader.launch (change tag_nr with your AR tag number)

   .. code-block:: bash
      
      roslaunch roslaunch robotont_demos ar_follow_the_leader.launch marker_id:=tag_nr

#. **On PC** launch ar_marker_display.launch to visualize the result

   .. code-block:: bash
      
      roslaunch robotont_demos ar_marker_display.launch

#. To move the robot open another terminal window **on Robotont on-board computer or on PC** and run teleop twist keyboard

   .. code-block:: bash
      
      roslaunch robotont_demos teleop_keyboard.launch
    
    
   .. hint:: Notice that the teleop node only receives keypresses when the terminal window is active.
