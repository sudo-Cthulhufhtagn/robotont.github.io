==========
Sound play
==========

Installing dependencies
-----------------------
.. warning:: 
  
    If your ROS version is noetic install for noetic
.. code-block:: bash

    sudo apt install ros-melodic-sound-play

Copy code to catkin_ws/src
--------------------------
    
.. code-block:: bash
    
    git clone https://github.com/sudo-Cthulhufhtagn/sound_box.git

Running code:
-------------

.. admonition:: First make sure that soundplay_node.py is up and running!

    rosrun sound_play soundplay_node.py

.. code-block:: bash
    
    rosrun sound_box first_words.py

Or just simply run this instead of previous code:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: bash
    
    roslaunch sound_box wake_up.launch

You can also run node which speaks when robot starts moving or reaches maximum speed
------------------------------------------------------------------------------------
    
.. code-block:: bash
        
    roslaunch sound_box speed_sniffer.launch

Autolaunch
----------
Modify **robotont_support/launch/bringup.launch** to make it speak every time it turns on by adding this line  :code:`<include file="$(find sound_box)/launch/wake_up.launch"/>`

