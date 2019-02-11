YARP-based simulation with cameras :tag:`yarp`
==============================================

This tutorial shows how to experiment with MORSE's cameras
and how to extract the images they capture.
You'll also be able to control the robot's movement, by giving
it the coordinates of its destination.

Setup
-----

You need to install YARP and its Python bindings, by following the YARP
section in the :doc:`installation notes <../installation/mw/yarp>`.

Before running a simulation using YARP, it is necessary to open a new shell
terminal and start the ``yarpserver3`` program::

  $ yarpserver3

Configuring the scenario
------------------------

We'll use the Builder API to create the scenario and configure the robot.
You can find the complete file in ``$MORSE_ROOT/share/morse/examples/tutorials/tutorial-2-yarp.py``.

The file itself is very similar to the one created in the :doc:`first tutorial <tutorial>`.
We will only add the camera, and change the middleware bindings to use YARP.

If you edit the existing file from the previous tutorial, after configuring the robot,
you can add the camera like this:

.. code-block:: python

  camera = VideoCamera()
  camera.translate(x=0.2, z=0.9)
  atrv.append(camera)

This will add a video camera at the top of the robot.

We will also change the motion controller, to show how to use a different
type of controller. We'll use the :doc:`waypoint <../actuators/waypoint>` controller,
which takes as input the coordinates of the robot's destination.

.. code-block:: python

    motion = Waypoint()
    atrv.append(motion)


Configuring the middlewares
+++++++++++++++++++++++++++

Next we need to tell MORSE how the components will communicate using middlewares.
This is done with these lines:

.. code-block:: python

  motion.add_stream('yarp')
  pose.add_stream('yarp')
  camera.add_stream('yarp')


Reading and writing data
------------------------

You can now launch the simulation by pressing :kbd:`p` on Blender's 3Dview.

When the simulation starts, it will print the names of the YARP ports that have
been created for every corresponding component. These port names can be used to
connect to the component from an external program or client.

Reading from sensors
++++++++++++++++++++

The simplest method to test the reading and writing of data is by using the
terminal clients. For example, to read the robot's Pose data through a port
named ``/morse/atrv/pose/out``, you can type the following in a
terminal::

  $ yarp read /data/in /morse/atrv/pose/out

Writing to actuators
++++++++++++++++++++

To enter the robot's destination coordinates, write them through a port
named ``/morse/atrv/motion/in``, using the command::

  $ yarp write /data/out /morse/atrv/motion/in

Then type the three destination coordinates, a toleration distance and the
movement speed, separated by spaces, and press :kbd:`Enter`. For example::

  5 7 0 0.5 2

Will make the robot move to within 0.5 meters of the coordinates (5.0, 7.0,
0.0), at a speed of 2 m/s.

Displaying an image from the camera
+++++++++++++++++++++++++++++++++++

YARP provides a tool to display the images it receives through a port. This is very
convenient to quickly test that you can transmit video from the simulated environment.
You first need to launch the viewer application::

  $ yarpview /img/read &

This creates a new port called ``/img/read``. Next you need to connect this
port to the MORSE output port that's dedicated to the camera,
``/morse/atrv/camera/out``. The connection is done with this command::

  $ yarp connect /morse/atrv/camera/out /img/read

Now you should be able to see the output of the camera mounted on
top of the robot.  Tell the robot to move, using the motion controller,
and you'll see the video image being updated.
