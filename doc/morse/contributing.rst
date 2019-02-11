Contributing to MORSE
=====================

Get involved!
-------------

As an open-source project driven by the research community, your 
contributions are very welcome!

You can write to the project's developers at this 
address: `morse-dev@laas.fr <mailto:morse-dev@laas.fr>`_.

MORSE development can be tracked on the `MORSE GitHub repository
<https://github.com/morse-simulator/morse>`_::

    git clone git://github.com/morse-simulator/morse.git

If you want your feature to be merged into MORSE:

- First, `fork <https://help.github.com/articles/fork-a-repo>`_ ``morse-simulator/morse``
  on GitHub.
- Then, `send a pull request
  <https://help.github.com/articles/using-pull-requests>`_ with your changes.

You can also get the source directly from the LAAS mirror repository at:
``git://git.openrobots.org/git/robots/morse``


Developers documentation
------------------------

Build status
++++++++++++

.. raw:: html

    <script
      type="text/javascript"
      src="https://ci.clf.cit-ec.de/view/MORSE/job/MorsePublic-1.0-master-build/jswidgets/health?skipDescription=true">
    </script>
    <script
      type="text/javascript"
      src="https://ci.clf.cit-ec.de/view/MORSE/job/MorsePublic-1.0-master-testing-BASE/jswidgets/health?skipDescription=true">
    </script>
    <script
      type="text/javascript"
      src="https://ci.clf.cit-ec.de/view/MORSE/job/MorsePublic-1.0-master-testing-ROBOTS/jswidgets/health?skipDescription=true">
    </script>
    <script
      type="text/javascript"
      src="https://ci.clf.cit-ec.de/view/MORSE/job/MorsePublic-1.0-master-testing-MIDDLEWARES/jswidgets/health?skipDescription=true">
    </script>
    <style type="text/css">
    div.healthReportDetails { align: center; background-color: rgba(1,1,1,0); border: 0px; width: auto;} /* fix css integration */
    div.healthReportDetails div { display:none;} /*hide Jenkins title */
    </style>


Extending Morse
+++++++++++++++

.. toctree::
    :maxdepth: 1

    dev/file_hierarchy
    dev/coding_guidelines
    dev/adding_component
    dev/adding_robot
    dev/adding_datastream_handler
    dev/adding_modifier
    dev/services
    dev/new_middleware
    dev/testing

Morse internals
+++++++++++++++

.. toctree::
    :maxdepth: 1

    dev/component_object_model
    dev/entry_point
    dev/execution_loop
    dev/arguments_passing
    dev/time_event
    dev/services_internal

Code reference
--------------

Automatically generated code reference is :doc:`accessible here <../user/code/morse>`.

Tips and how-to 
---------------

.. toctree::
    :glob:
    :maxdepth: 1

    user/tips/*
