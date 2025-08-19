Usage Examples
==============

Basic Connection
----------------

Connect to an IPIO device and authenticate:

.. code-block:: python

    from ipio import IPIO
    from ipio.pin_state import PinState
    
    # Connect to IPIO device
    ipio = IPIO('192.168.1.100', 'admin', 'password', 502)

Digital Output Control
----------------------

Control individual outputs:

.. code-block:: python

    # Turn on output pin 1
    ipio.set_output(1, PinState.HIGH.value)
    
    # Turn off output pin 1
    ipio.set_output(1, PinState.LOW.value)
    
    # Pulse output pin 1
    ipio.set_output(1, PinState.PULSE.value)

Bulk Output Operations
----------------------

Control multiple outputs simultaneously:

.. code-block:: python

    # Set all 8 outputs (first 4 on, last 4 off)
    ipio.set_output_as_bulk("11110000")
    
    # Get current state of all outputs
    output_states = ipio.get_output_as_bulk()

Digital Input Reading
---------------------

Read input states:

.. code-block:: python

    # Read single input
    input_state = ipio.get_input(1)
    
    # Read all inputs
    all_inputs = ipio.get_input_as_bulk()

Configuration Management
------------------------

Update device configuration:

.. code-block:: python

    # Set device IP address
    ipio.set_ip('192.168.1.101', '255.255.255.0', '192.168.1.1')
    
    # Get current IP configuration
    ip_config = ipio.get_ip()

Error Handling
--------------

Handle common exceptions:

.. code-block:: python

    from ipio.exceptions import *
    
    try:
        ipio = IPIO('192.168.1.100', 'admin', 'password', 502)
        ipio.set_output(1, PinState.HIGH.value)
    except WrongCredentialsException:
        print("Invalid credentials")
    except NotConnectedException:
        print("Device not connected")
    except Exception as e:
        print(f"Unexpected error: {e}")
    finally:
        ipio.close()

