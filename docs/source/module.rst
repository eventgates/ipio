API Reference
=============

The IPIO library provides a simple Python interface for controlling IPIO industrial I/O devices.

Main Classes
------------

.. toctree::
    :titlesonly:
    :maxdepth: 2

    ipio

Constants and Enums
-------------------

The library includes several modules with constants and enums:

* **PinState**: Enumeration for pin states (LOW, HIGH, PULSE, NO_CHANGE)
* **Device**: Device type constants (STM32, W5500)
* **ApiMethod**: Protocol command constants
* **ConfigField**: Configuration parameter constants

Exceptions
----------

Custom exceptions for error handling:

* **NotConnectedException**: Raised when device is not connected
* **WrongCredentialsException**: Raised for authentication failures
* **MutedSystemException**: Raised when system is muted
* **UnknownApiMethodException**: Raised for invalid API methods
* **ValidationException**: Raised for parameter validation errors

