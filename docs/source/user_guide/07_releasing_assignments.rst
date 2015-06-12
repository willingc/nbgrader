
Releasing assignments
=====================

.. seealso::

    :doc:`03_generating_assignments`
        Details on generating assignments

    :doc:`/command_line_tools/nbgrader-release`
        Command line options for ``nbgrader release``

    :doc:`/command_line_tools/nbgrader-list`
        Command line options for ``nbgrader list``

After an assignment has been created using ``nbgrader assign``, the
instructor must actually release that assignment to students. If the
class is being taught on a single filesystem, then the instructor may
use ``nbgrader release`` to copy the assignment files to a shared
location on the filesystem for students to then download.

First, we must specify a few configuration options. We'll need to use
these a few times, so we'll create a ``nbgrader_config.py`` file that
will get automatically loaded when we run ``nbgrader``:

.. code:: python

    %%file nbgrader_config.py
    
    c = get_config()
    
    c.NbGraderConfig.course_id = "example_course"
    c.TransferApp.exchange_directory = "/tmp/exchange"


.. parsed-literal::

    Writing nbgrader_config.py


In the config file, we've specified the "exchange" directory to be
``/tmp/exchange``. This directory must exist before running
``nbgrader``, so we'll first create it:

.. code:: python

    %%bash
    
    # remove existing directory, so we can start fresh for demo purposes
    rm -rf /tmp/exchange
    
    # create the exchange directory, with write permissions for everyone
    mkdir /tmp/exchange
    chmod og+w /tmp/exchange

Now that we have the directory created, we can actually run
``nbgrader release``:

.. code:: python

    %%bash
    
    nbgrader release "Problem Set 1"


.. parsed-literal::

    [ReleaseApp | INFO] Source: /home/travis/build/jupyter/nbgrader/docs/source/user_guide/release/Problem Set 1
    [ReleaseApp | INFO] Destination: /tmp/exchange/example_course/outbound/Problem Set 1
    [ReleaseApp | INFO] Released as: example_course Problem Set 1


Finally, you can verify that the assignment has been appropriatel
released by running the ``nbgrader list`` command:

.. code:: python

    %%bash
    
    nbgrader list


.. parsed-literal::

    [ListApp | INFO] Released assignments:
    [ListApp | INFO] example_course Problem Set 1

