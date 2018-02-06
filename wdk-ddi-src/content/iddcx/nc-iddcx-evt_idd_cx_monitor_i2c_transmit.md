---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_I2C_TRANSMIT
title: EVT_IDD_CX_MONITOR_I2C_TRANSMIT
author: windows-driver-content
description: EVT_IDD_CX_MONITOR_I2C_TRANSMIT is called by the OS to return data received to an I2C device in a monitor.
old-location: display\evt_idd_cx_monitor_i2c_transmit.htm
old-project: display
ms.assetid: d36d45f5-fae1-430a-a01e-adb70e09573c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.evt_idd_cx_monitor_i2c_transmit, EvtIddCxMonitorI2cTransmit callback function [Display Devices], EvtIddCxMonitorI2cTransmit, EVT_IDD_CX_MONITOR_I2C_TRANSMIT, EVT_IDD_CX_MONITOR_I2C_TRANSMIT, iddcx/EvtIddCxMonitorI2cTransmit, PFN_IDD_CX_MONITOR_I2C_TRANSMIT callback function pointer [Display Devices], PFN_IDD_CX_MONITOR_I2C_TRANSMIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "_requires_same_"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	iddcx.h
apiname:
-	PFN_IDD_CX_MONITOR_I2C_TRANSMIT
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---


# EVT_IDD_CX_MONITOR_I2C_TRANSMIT function
<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> is called by the OS to return data received to an I2C device in a monitor.

## Syntax

```
EVT_IDD_CX_MONITOR_I2C_TRANSMIT EvtIddCxMonitorI2cTransmit;

_IRQL_requires_same_ NTSTATUS EvtIddCxMonitorI2cTransmit(
  IDDCX_MONITOR MonitorObject,
  const IDARG_IN_I2C_TRANSMIT * pInArgs
)
{...}
```

## Parameters

`MonitorObject`

A handle used by the OS to identify the monitor to return I2C data to.

`pInArgs`

Input arguments used by <b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b>.


## Return Value

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## Remarks

<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> is responsible for signaling the I2C start condition, sending the I2C address, sending the data in the buffer, checking for acknowledgments from the receiver, and signaling the stop condition. For details about the I2C bus, see the I2C Bus Specification, published by Philips Semiconductors. The specification defines a protocol for initiating I2C communication, reading and writing bytes over the I2C data line, and terminating I2C
communication.


<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> is required to transmit data to an I2C device that has address 0x6E but is permitted to refuse to transmit data to any I2C device that has a different address.


<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> is permitted to block if another part of the display driver or graphics hardware is using the specified monitor's I2C bus. It is also permitted to block if the display driver is using the I2C bus to send or receive High-bandwidth Digital Content Protection (HDCP) data.
<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> has a 5 second timeout and must complete in that time limit.

If the display adapter supports HDCP, <b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> must refuse to send data to an I2C device if the device has an I2C address that is used by HDCP.
<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> must never transmit data to an I2C device on the display adapter. That is, this function can transmit data to an I2C device in a monitor that is connected to the display adapter, but not to an I2C device that is on the display adapter itself.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | iddcx.h |
| **IRQL** | "_requires_same_" |