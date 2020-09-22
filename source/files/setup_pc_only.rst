##############################
Using only the simulated robot
##############################

Installing Ubuntu
-----------------

Download and install Ubuntu Linux on your PC from the following link: `Ubuntu 18.04.4 LTS (Bionic Beaver) <http://releases.ubuntu.com/18.04.4/?_ga=2.170843936.1678816316.1594710587-1973467440.1591964081>`__.

The guide to install Ubuntu on your PC can be found `here <https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview>`__.

Installing ROS
--------------

Install Ros Melodic by following the guide: `Ros Melodic <http://wiki.ros.org/melodic/Installation/Ubuntu>`__.

Creating a catkin workspace
----------------------------

Create a workspace for catkin as shown `here <http://wiki.ros.org/catkin/Tutorials/create_a_workspace>`__.

Cloning Robotont's packages
-----------------------------

All Robotont's packages can be accessed from `Robotont's GitHub <https://github.com/robotont>`__.

To clone the packages:

.. code-block:: bash
      
    git clone https://github.com/robotont/package_name.git

Building the catkin workspace
------------------------------

.. code-block:: bash
      
    cd catkin_ws
    catkin build

Sourcing the workspace
-----------------------

Make the workspace visible to ROS (must be done for every new terminal)

.. code-block:: bash

      source ~/catkin_ws/devel/setup.bash

For automatic sourcing:

.. code-block:: bash

      echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc



    


