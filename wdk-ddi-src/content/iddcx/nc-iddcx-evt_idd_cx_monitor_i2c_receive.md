---
UID : NC:iddcx.EVT_IDD_CX_MONITOR_I2C_RECEIVE
title : EVT_IDD_CX_MONITOR_I2C_RECEIVE
author : windows-driver-content
description : EVT_IDD_CX_MONITOR_I2C_RECEIVE is called by the OS to return data received from an I2C device in a monitor.
old-location : display\evt_idd_cx_monitor_i2c_receive.htm
old-project : display
ms.assetid : f4d55fb9-57da-4f75-a0ab-89cc9516ac49
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : WcsTranslateColors
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : iddcx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PFN_IDD_CX_MONITOR_I2C_RECEIVE
req.alt-loc : iddcx.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : _requires_same_
req.typenames : WCS_PROFILE_MANAGEMENT_SCOPE
---


# EVT_IDD_CX_MONITOR_I2C_RECEIVE function
<b>EVT_IDD_CX_MONITOR_I2C_RECEIVE</b> is called by the OS to return data received from an I2C device in a monitor.

## Syntax

```
EVT_IDD_CX_MONITOR_I2C_RECEIVE EvtIddCxMonitorI2cReceive;

_IRQL_requires_same_ NTSTATUS EvtIddCxMonitorI2cReceive(
  IDDCX_MONITOR MonitorObject,
  const IDARG_IN_I2C_RECEIVE * pInArgs
)
{...}
```

## Parameters

`MonitorObject`

A handle used by the OS to identify the monitor to receive I2C data from.

`pInArgs`

Input arguments used by <b>EVT_IDD_CX_MONITOR_I2C_RECEIVE</b>.


## Return Value

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## Remarks

The <b>EVT_IDD_CX_MONITOR_I2C_RECEIVE</b> function is responsible for signaling the I2C start condition, sending the I2C address,
 receiving the data from the I2C device, sending acknowledgments, and signaling the stop condition.
 For details about the I2C bus, see the I2C Bus Specification, published by Philips Semiconductors.
 The specification defines a protocol for initiating I2C communication, reading and writing bytes over the I2C data
 line, and terminating I2C communication. (This resource may not be available in some languages and countries.)


<b>EVT_IDD_CX_MONITOR_I2C_RECEIVE</b> is required to receive data from an I2C device that has address 0x6F, but is
 permitted to refuse to receive data from any I2C device that has a different address.
 

<b>EVT_IDD_CX_MONITOR_I2C_RECEIVE</b> is permitted to block if another part of the display driver or graphics hardware is
 using the specified monitor's I2C bus. It is also permitted to block if the display driver is using the I2C bus to send or receive High-bandwidth Digital Content Protection (HDCP) data.
 <b>EVT_IDD_CX_MONITOR_I2C_RECEIVE</b> has a 5 second timeout and must complete in that time limit.

If the display adapter supports HDCP, <b>EVT_IDD_CX_MONITOR_I2C_RECIEVE</b> must refuse to receive data from an I2C device if the
 device has an I2C address that is used by HDCP.
 This function  can receive data from an I2C device in a monitor that is connected to the display adapter, but must never receive data from an I2C
 device that is on the display adapter itself.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iddcx.h |
| **Library** |  |
| **IRQL** | _requires_same_ |
| **DDI compliance rules** |  |