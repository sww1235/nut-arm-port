# nut-arm-port
Port of Network UPS Tools (NUT) to nearly bare metal ARM Cortex

## NOTE:

This project has been customized more or less to my specific use cases. I am
using this as a learning opportunity for embedded development on ARM Cortex
with C and a RTOS. I will endevour to keep things as generic as possible, but
nothing is guarenteed.  

## Introduction

In the case of monitoring a small number of UPSes connected via USB either:

Running a UPS monitoring Daemon on a server also running other services is
antithetical to the Unix philosophy of doing one thing and doing it well.

or

Running a UPS monitoring Daemon on an embedded box with a full os introduces a
multitude of extra dependancies and potential vulnerabilities to the system.

Both these options also add in additional power consumption which can reduce UPS runtime.

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

The use of FreeRTOS will allow for easier migration between vendors and models
of microprocessors. IO libraries will only be present for the chips I am
targeting. If others wish to contribute to these libraries, pull requests are
welcome.

## Hardware

In theory, this can be run on any dev board that supports the necessary
interfaces to connect to the computer and UPS, normally TCP, USB and serial. I
am developing a dedicated microcontroller that will use as little power as
possible, with only the needed interfaces broken out. It will be open sourced,
and linked here eventually.

## Dependancies

-	FreeRTOS
-	FreeRTOS+TCP TCP Stack


## Code Citations

A lot of the code in this repository will be copied from the NUT repository
wholesale and then extensively modified. As a way of attempting to provide some
tracibility and not plagerize, I intend to copy all code into the repository in
full with an initial commit referencing where it came from, and then modify it
if necessary.
