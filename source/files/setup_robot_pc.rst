##############################
Using the robot with a user PC
##############################

Setting up the PC
======================

Installing Ubuntu
-----------------

Download and install Ubuntu Linux on your PC from the following link: `Ubuntu 18.04.4 LTS (Bionic Beaver) <http://releases.ubuntu.com/18.04.4/?_ga=2.170843936.1678816316.1594710587-1973467440.1591964081>`__.

The guide to install Ubuntu on your PC can be found `here <https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview>`__.

Installing ROS
--------------

Install Ros Melodic according to the following link: `Ros Melodic <http://wiki.ros.org/melodic/Installation/Ubuntu>`__.


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

.. _connecting-remotely:

Connecting with the robot remotely
===================================

1. Open a new terminal window

2. Connect the user PC to Robotont's network or make sure that the user PC and Robotont's on-board computer are connected to the same wifi router 

  .. image:: /files/pictures/wifi_screen.png
    :width: 400

3. Establish an ssh connection (change the X with the ID written on the robot)

   .. code-block:: bash
      
      ssh kasutaja@clearbot-X

  or 

  .. code-block:: bash
      
      ssh kasutaja@ip_of_the_robot

  .. image:: /files/pictures/ssh_nt.png
    :width: 400

4. If a yes/no question is asked, enter yes

5. Enter the password


6. When logged in successfully, you can see that the terminal prompt has changed to kasutaja@clearbot-X. This will be an important reference when trying to figure out which terminal is connected to where.

  .. image:: /files/pictures/ssh_nt2.png
    :width: 400

7. After logging into the robot, the ROS environment should be automatically sourced for you. You can quickly display the last lines of the file with tail ~/.bashrc command to examine which workspaces are sourced.


Getting the Robotont and PC into the same ROS environment
=========================================================

There are two approaches to get the Robotont and PC into the same ROS environment. A common prerequisite for both methods is that the hosts are connected to the same network. In the following examples, we assume the Robotont and the PC having the following configuration:

.. csv-table::
  :header: "Machine", "Hostname", "IP-address"
  :widths: 40, 40, 40

  "Robotont", "clearbot-1", "192.168.1.1"
  "PC", "laptop-1", "192.168.1.101"

Hostname based setup
--------------------

In this configuration, the robot and PC query each other via hostnames. It means that both hosts need to have each other's names associated with IP addresses. These hostname <--> IP pairs are defined in the `/etc/hosts` file. Use your favorite text editor and make sure the following entries exist.

**/etc/hosts on Robotont on-board computer:**

.. code-block:: bash

  127.0.1.1 clearbot-1
  192.168.1.101 laptop-1


**/etc/hosts on PC:**

.. code-block:: bash

  127.0.1.1 laptop-1
  192.168.1.1 clearbot-1


Next, we need to tell the PC to look for a ROS Master on Robotont. We do that by modifying a special environment variable named `ROS_MASTER_URI`, which by default points to localhost.

**on PC**, open a terminal and enter:

.. code-block:: bash

  export ROS_MASTER_URI=http://robotont-1:11311

Now all ROS nodes you run in this terminal will connect to the Master on the Robotont. Test it with e.g. `rosnode list`.
Note that the environment variable has to be set for each terminal window! To make it automatic, you can add the line to the end of the `.bashrc` file in the home directory of the PC:

.. code-block:: bash

  echo 'export ROS_MASTER_URI=http://robotont-1:11311' >> ~/.bashrc


IP-address based setup
----------------------
If you want to configure IP based communication there is no need to edit the hosts file. Instead, a `ROS_IP` environmental variable has to be set on both sides:

**on Robotont on-board computer:**

.. code-block:: bash

  export ROS_IP=192.168.200.1


**on PC:**

.. code-block:: bash

  export ROS_MASTER_URI=http://192.168.200.1:11311
  export ROS_IP=192.168.200.101


Similarly to the hostname based setup, append the commands to `.bashrc` to set the variables automatically.