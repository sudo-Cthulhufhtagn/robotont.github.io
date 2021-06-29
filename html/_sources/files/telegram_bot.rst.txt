############
Telegram bot
############
Installing dependencies
=======================

.. code-block:: bash

    pip install pyTelegramBotAPI

Copying code to catkin_ws
=========================

.. code-block:: bash

    https://github.com/sudo-Cthulhufhtagn/telegram_bot.git

How to use
==========
.. warning::

    First check that the bot has token and **only after that** run

1. On the robotont side run:
   
.. code-block:: bash
     
    rosrun telegram_bot bot.py

2. On the user's side open `bot <http://t.me/robotont_remote_control_bot>`__ and press start

Interface view
==============

You can launch keyboard either by manually typing :code:`/keyboard` or just pressing it in telegram welcome meassage, or also from bot menu in the down left corner

.. image:: /files/pictures/telegram_bot_interface1.jpg
    :width: 400

Central button allows to switch between keyboards

.. image:: /files/pictures/telegram_bot_interface2.jpg
    :width: 400


Live example:
=============

.. raw:: html

    <iframe width="560" height="315" src="https://www.youtube.com/embed/OibVwBPJXsc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>