AVR Makefile Project Template
=============================

This project has been designed to be the starting point for Makefile based
projects for 8-bit Atmel AVR micro controllers.

Toolchain Installation
----------------------

Basically, this project template requires `GNU Make`, and a `GCC` based AVR
toolchain. In the following, installation guides for different platforms are
presented. In general, the following tools are required:

+--------------+--------------------------------------------------+
| Tool         | Note                                             |
+==============+==================================================+
| GNU Make     | ---                                              |
+--------------+--------------------------------------------------+
| AVR GCC      | Version depending on your preferred C++ standard |
+--------------+--------------------------------------------------+
| AVR libc     | ---                                              |
+--------------+--------------------------------------------------+
| AVR binutils | ---                                              |
+--------------+--------------------------------------------------+

Arch Linux
^^^^^^^^^^

The following packages provide the necessary tools:

+------------------------+--------------+------------+
| Package                | Tool         | Group      |
+========================+==============+============+
| core/make              | GNU make     | base-devel |
+------------------------+--------------+------------+
| community/avr-gcc      | AVR GCC      | ---        |
+------------------------+--------------+------------+
| community/avr-libc     | AVR libc     | ---        |
+------------------------+--------------+------------+
| community/avr-binutils | AVR binutils | ---        |
+------------------------+--------------+------------+

Customizing the Build
---------------------

The makefile of this template provides several variable that allow you to
customize/adjust the build process:

Product Settings
^^^^^^^^^^^^^^^^

**TARGET**
    The name of the resulting HEX and BIN files

    *default:* **firmware**

Platform Settings
^^^^^^^^^^^^^^^^^

**CLOCK**
    The clock frequency in hertz of your target system

    *default:* **16000000** (16 MHz)

**MCU**
    The type of MCU of your target system

    *default:* **atmega328p**

Toolchain Settings
^^^^^^^^^^^^^^^^^^

**TPREFIX**
    The prefix for the tools of your AVR toolchain

    *default:* **avr-**

**AVRSIZE**
    The name of the `size` utility for AVR

    *default:* **size**

**COMPILE**
    The name of the AVR compiler

    *default:* **g++**

**OBJCOPY**
    The name of the AVR object copy executable for hex-file generation

    *default:* **objcopy**

**OBJDUMP**
    The name of the AVR object dump executable for disassembling the bin-file

    *default:* **objdump**

Build Settings
^^^^^^^^^^^^^^

**CXXFLAGS**
    User defined additional compiler flags

    *default:* **-std=gnu++17**

**LDFLAGS**
    User define additional linker flags

    *default:*

Sources and Include Paths
^^^^^^^^^^^^^^^^^^^^^^^^^

**SRCDIR**
    The source root of the project

    *default:* **src**

**PINCIDRS**
    A list of project local include directories

    *default:* **include**

**SINCIDRS**
    A list of system include directories

    *default:*

**SRCS**
    A list of source files, relative to the source directory

    *default:* **avr**

User-facing Make Goals
----------------------

The makefile shipping with this template provides the following goals:

**all**
    Checks if all tools are available and builds the firmware hex-file

**clean**
    Removes build products from the source tree

**dist-clean**
    Removes the product folders as well as the toolchain check-file

**disasm**
    Builds the firmware and provides a source-interspersed disassembly

**size**
    Build the firmware and provides size statistics

All other goals of the makefile a discouraged to be used directly and are
subject to change without prior announcement.
