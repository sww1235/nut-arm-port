# nut-arm-port
Port of Network UPS Tools (NUT) to nearly bare metal ARM Cortex

In the case of monitoring a small number of UPSes connected via USB either:

Running a UPS monitoring Daemon on a server also running other services is
antithetical to the Unix philosophy of doing one thing and doing it well.

or

Running a UPS monitoring Daemon on an embedded box with a full os introduces a
multitude of extra dependancies and potential vulnerabilities to the system.

What is needed, is a single purpose, dedicated piece of hardware that runs the
UPS monitoring Daemon and server in real time as close to bare metal as
possible. No weirdness with services, upgrading network stacks, pid files,
config files, etc. If you are only monitoring a couple devices in one physical
location, then you can strip all that out and just break down the Daemon to its
esential parts.

This repository is an attempt to port the [Network UPS Tools
(NUT)](https://github.com/networkupstools/nut) server and some of the drivers
to bare metal ARM Cortex running in FreeRTOS due to the need for a network
stack.

## Dependancies

-	FreeRTOS
-	FreeRTOS+TCP TCP Stack
