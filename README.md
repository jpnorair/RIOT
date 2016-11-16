OT+RIOT is a hybrid RTOS for wireless IoT that combines:
* [OpenTag](https://github.com/jpnorair/OpenTag): "The ultra-low-latency DASH7 IoT RTOS"
* [RIOT](https://github.com/RIOT-OS/RIOT): "The friendly Operating System for IoT!"

Follow the two links above to get more information on the respective projects.

The goal of OT+RIOT is to provide a kinder, gentler application development environment to OpenTag, while retaining the high performance of OpenTag for DASH7-based networking.  In this architecture, OpenTag acts as a BIOS, including intrinsic DASH7 functionality, and RIOT sits on top.  
* The performance penalty to RIOT and its traditional apps is negligible (often nothing at all).
* OpenTag provides asynchronous tasking to its tasks/threads.  These are usually limited to DASH7 and other minimal, low-level features.  RIOT tasks can interface with OpenTag through an API designed simply to configure, execute, and get results.
* OpenTag provides a tickless event to activate RIOT.  While RIOT is running, it uses a synchronous tick.  This allows "best of both worlds" features to RIOT apps.
* OpenTag provides a DASH7-based wireless bootloader option to the RIOT system.
* Most pre-existing RIOT apps and stacks should work without issue, allowing multi-function devices.  Only those that require direct access to hardware resources used by the OpenTag BIOS must be ported.
