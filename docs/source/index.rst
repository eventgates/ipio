IPIO Python Library
====================

.. image:: https://github.com/eventgates/ipio/blob/master/ipio.jpg?raw=true

IPIO is a Python library for controlling IPIO industrial I/O devices. These devices provide 8 digital outputs and 4 digital inputs via TCP socket communication, designed for industrial automation applications.

Features
--------

* **Digital I/O Control**: Control 8 digital outputs and read 4 digital inputs
* **Bulk Operations**: Efficient bulk read/write operations for multiple pins
* **Device Configuration**: Network settings, user management, and operational parameters
* **Real-time Monitoring**: Device status monitoring and log retrieval
* **Firmware Updates**: Over-the-network firmware updates with integrity verification
* **Error Handling**: Comprehensive exception handling for robust applications

Quick Start
-----------

Install with pip (requires Python 3.6+):

.. code-block:: bash

    pip install ipio

Basic usage:

.. code-block:: python

    from ipio import IPIO
    from ipio.pin_state import PinState
    
    # Connect to device
    ipio = IPIO('192.168.1.100', 'admin', 'password', 502)
    
    # Control outputs
    ipio.set_output(1, PinState.HIGH.value)  # Turn on output 1
    ipio.set_output_as_bulk("11110000")      # Control all outputs
    
    # Read inputs
    input_state = ipio.get_input(1)          # Read input 1
    all_inputs = ipio.get_input_as_bulk()    # Read all inputs

.. toctree::
    :caption: Contents:
    :titlesonly:

    module
    examples
    license

.. toctree::
    :hidden:
    :caption: Links:
    :titlesonly:

    EventGates <https://eventgates.com>
    GitHub <https://github.com/eventgates/ipio.git>
    PyPi <https://pypi.org/project/ipio/>
