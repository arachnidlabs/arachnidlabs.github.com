---
layout: page-side
title: "USB Interface Protocol"
date: 2014-09-28 17:30
comments: true
sharing: true
footer: true
section: reload-pro
---
The Re:load Pro features a USB interface with serial port emulation (CDC), which
supports a straightforward text-based protocol for controlling and monitoring
the Re:load Pro and the attached test device. The Re:load Pro's serial interface
operates at 115200 baud 8/n/1.

Both commands and responses are line-based. Responses from the Re:load Pro are
terminated with "\r\n", and commands to the Re:load Pro need only be terminated
with "\n" ("\r" will be silently ignored).

All commands generate at least one response line from the Re:load Pro. Some
commands may generate multiple responses, and some conditions, such as interval
monitoring, overtemperature and undervoltage may trigger unsolicited response
lines from the Re:load Pro. Programs implementing the protocol should expect
that they may receive such responses at any time, and code accordingly.

Commands and arguments are case-sensitive.

# Command reference

## bl
Enters bootloader/firmware upgrade mode. Emits an 'ok' response, then enters
bootloader mode. Any further serial communication will be received by the
bootloader.

## set [I]
Sets the current setpoint to I, expressed in milliamps. Responds with a 'set'
response with the new current setpoint. This may differ from the provided
setpoint if the provided setpoint was less than 0 or greater than the maximum
supported current.

If I is not provided, reports the current setpoint without altering it.

## mode MODE
Sets operating mode. Currently only 'cc' for constant current mode is supported.
Responds with a 'mode' response with the new operating mode.

## read
Returns a 'read' response with the voltage and current across the Re:load Pro.

## reset
When the Re:load Pro has disabled itself due to overtemperature or undervoltage,
the 'reset' command sets the current setpoint to 0 and returns to normal operation.
Returns an 'ok' response.

## monitor INTERVAL
Enables monitoring with an interval of INTERVAL milliseconds. Every x milliseconds, a
'read' response will be returned until 'monitor 0' is sent to cease monitoring.
The first response will occur after INTERVAL milliseconds, rather than immediately.

## debug
Outputs a series of debugging information lines as 'info' messages.

## cal SUBCOMMAND [arg]
Calibration master command. Supports several subcommands:

### cal o
Calibrates ADC offsets. Sets ADC offset to the currently observed voltage and
current, and returns 'ok'. Only run with no leads attached to the Re:Load Pro.

### cal v VOLTAGE
Calibrates the ADC's voltage gain. VOLTAGE should be the voltage across the
Re:load Pro. Responds with 'ok'.

### cal i CURRENT
Calibrates the ADC's current gain. CURRENT should be the current across the
Re:load Pro. Responds with 'ok'.

### cal d CURRENT
Performs automatic DAC opamp offset trim, offset, and gain calibration based
on the calibrated output of the ADC. Responds with 'ok'. CURRENT is the maximum
test current level to use in calibration.

From v1.6: No longer performs opamp offset trim calibration; this is now done
with 'cal t' or manually with 'cal O'

### cal O [OFFSET]
Without an argument, returns the current opamp offset trim value, between 0 and
63 with a 'cal O' response. With an argument, sets the opamp offset trim.

### cal t CURRENT
Performs automatic opamp offset trim calibration. Responds with 'ok'. CURRENT
is the maximum test current level to use in calibration.

## version
From v1.6: Returns the current firmware version number in a 'version' response.

# Response reference

## read CURRENT VOLTAGE
Returns the current and voltage across the Re:load Pro, in millivolts.

## err MESSAGE
Sent when an invalid command was sent. MESSAGE is a human-readable message
describing the problem.

## mode MODE
Returns the current operating mode. Currently this will always be 'cc'.

## set I
Returns the current setpoint.

## ok
Indicates your command was received and acted on successfully.

## info
Provides a human-readable information message about the Re:load Pro. Currently
only used in response to the 'debug' command.

## cal O OFFSET
Returns the opamp offset trim value for the Re:load Pro's internal opamp in
response to a 'cal O' command.

## overtemp
Sent unsolicited when the FET in the Re:load Pro goes into overtemperature
shutdown. Issue a 'reset' command to set the current setpoint to 0 and resume
normal operation.

## undervolt
Sent unsolicited when the Re:load Pro detects an undervoltage condition. Issue a
'reset' command to set the current setpoint to 0 and resume normal operation.

## version
Returned in response to a 'version' command. Reports the current firmware version
in dotted-decimal format.
