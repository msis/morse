ROS Installation Notes
~~~~~~~~~~~~~~~~~~~~~~

**These ROS installation notes are only useful if the default installation does
not work for you** (for instance, you are running on an older version of Ubuntu
or Debian).

If the packages ``python3-catkin-tools`` and
``python3-yaml`` are available for your distribution, install them, and
that should be sufficient. In this case you're ready to read
:doc:`the ROS + MORSE tutorial <../../../user/beginner_tutorials/ros_tutorial>`.


Otherwise, follow these steps to install them manually:

#. Install ROS and run ``sudo rosdep init`` and ``rosdep update``
   as explained in the `installation wiki <http://wiki.ros.org/indigo/Installation/Ubuntu#Initialize_rosdep>`_

#. Install Python 3 using your system package manager (available in Ubuntu >=
   11.04) or manually from the source, and make sure your ``$PYTHONPATH``
   variable includes the Python 3 libraries::

        sudo apt-get install python3-dev

#. Install ``PyYAML`` with Python 3 support::

        sudo apt-get install python3-yaml

   or get it via ``pip``  the sources from http://pyyaml.org and build it using python3::

        pip3 install pyyaml

#. Install catkin with Python 3 support::

    pip3 install catkin_pkg rospkg

#. Open a terminal and check if everything is correctly set. Therefore, open
   a terminal and type:

   ``morse check``

   If successful, the following line will be printed after some other information 
   about your configuration:

   ``* Your environment is correctly setup to run MORSE.``

Now you can start having fun with MORSE and ROS! For example, start reading
:doc:`the ROS + MORSE tutorial <../../../user/beginner_tutorials/ros_tutorial>`.


