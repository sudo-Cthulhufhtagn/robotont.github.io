###############
Demos on Gazebo
###############

Before getting started see: :ref:`before_starting`.

Launching the Simulation
------------------------

#. To launch the simulator: 

   .. code-block:: bash
      
      roslaunch robotont_gazebo gazebo.launch


There are two arguments on the launch file, that change the map and the position, where the robot will spawn: 

* world - the map where the robot will spawn, the default map is empty world

* x_pos - x coordinate of the map, controls where the robot will spawn


For example, the following command will spawn the robot to a map called minimaze.world in position x=2:
   
   .. code-block:: bash

      roslaunch robotont_gazebo gazebo_teleop_keyboard.launch world:=$(rospack find robotont_gazebo)/worlds/bangbang.world x_pos:=2


Maps
----

#. minimaze.world

   .. image:: /files/pictures/maze.png
      :width: 400

   To run

   .. code-block:: bash
      
      roslaunch robotont_gazebo gazebo_world_minimaze.launch

#. bangbang.world

   .. image:: /files/pictures/bangbang.png
      :width: 400

   To run 

   .. code-block:: bash
      
      roslaunch robotont_gazebo gazebo_world_between.launch

#. between.world

   .. image:: /files/pictures/between.png
      :width: 400

   To run

   .. code-block:: bash
      
      roslaunch robotont_gazebo gazebo_world_bangbang.launch


2D Mapping
-----------
Uses Cartographer to create a 2D map of the robot's surroundings.

#. Launch the simulator

   .. code-block:: bash
      
      roslaunch robotont_gazebo gazebo_world_minimaze.launch

#. Launch teleop keyboard

   .. code-block:: bash
      
      roslaunch robotont_demos teleop_keyboard.launch 

#. Launch 2d_slam.launch

   .. code-block:: bash
      
      roslaunch robotont_demos 2d_slam.launch

#. Display the map on RViz

   .. code-block:: bash
      
      roslaunch robotont_demos 2d_slam_display.launch
 

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
