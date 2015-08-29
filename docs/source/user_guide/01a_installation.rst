
Installation
============

Installing nbgrader command line tool
-------------------------------------

The current version of nbgrader installs simply with:

.. code:: bash

    pip install nbgrader

To upgrade a prior version of nbgrader:

.. code:: bash

    pip install --upgrade nbgrader


.. installing_toolbar::

Installing nbgrader's Jupyter toolbar extension
---------------------------------------------
You can then install and activate the nbgrader assignment toolbar extension with:

.. code:: bash

    nbgrader extension install
    nbgrader extension activate

Optional:  To install the extension for only yourself and not systemwide, use:

.. code:: bash

    nbgrader extension install --user

Optional:  If you don't wish to reinstall the extension when nbgrader is
upgraded, you may install the extension with a symbolic link to the nbgrader
command line tool:

.. code:: bash

    nbgrader extension install --symlink

To access help or to see the options supported for installation and activation
of the nbgrader notebook extension, use:

.. code:: bash

    nbgrader extension install --help-all
    nbgrader extension activate --help-all
