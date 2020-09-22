###############
Demos on Gazebo
###############


Launching the Simulation
------------------------

#. To launch the simulator: 

   .. code-block:: bash
      
      roslaunch robotont_gazebo gazebo_teleop_keyboard.launch

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

gmapping
********

#. Launch the simulator

   .. code-block:: bash
      
      roslaunch robotont_gazebo gazebo_world_minimaze.launch

#. Launch the gmapping software and visualize the map on RViz

   .. code-block:: bash
      
      roslaunch robotont_gazebo gazebo_gmapping.launch

#. Drive around using the keyboard and map the world

Google Cartographer
*******************
#. Launch the simulator

   .. code-block:: bash
      
      roslaunch robotont_gazebo gazebo_world_minimaze.launch

#. Launch Google Cartographer software and visualize the map on RViz

   .. code-block:: bash
      
      roslaunch robotont_gazebo 2d_nav_carto_gazebo.launch
    
#. Drive around using the keyboard and map the world


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