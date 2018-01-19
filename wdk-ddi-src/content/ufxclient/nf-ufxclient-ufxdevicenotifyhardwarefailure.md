---
UID : NF:ufxclient.UfxDeviceNotifyHardwareFailure
title : UfxDeviceNotifyHardwareFailure function
author : windows-driver-content
description : Notifies UFX about a non-recoverable hardware failure in the controller.
old-location : buses\ufxdevicenotifyhardwarefailure.htm
old-project : usbref
ms.assetid : 2EEA262C-5186-4450-A01D-212278ED710B
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : UfxDeviceNotifyHardwareFailure
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ufxclient.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : UfxDeviceNotifyHardwareFailure
req.alt-loc : ufxclient.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : DISPATCH_LEVEL
req.typenames : UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product : Windows 10 or later.
---


# UfxDeviceNotifyHardwareFailure function
Notifies UFX about a non-recoverable hardware failure in the controller.

## Syntax

````
VOID UfxDeviceNotifyHardwareFailure(
  [in]           UFXDEVICE                     UfxDevice,
  [in, optional] PUFX_HARDWARE_FAILURE_CONTEXT HardwareFailureContext
);
````

## Parameters

`UfxDevice`

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.

`HardwareFailureContext`

Optional pointer to a client driver-defined <a href="..\ufxbase\ns-ufxbase-_ufx_hardware_failure_context.md">UFX_HARDWARE_FAILURE_CONTEXT</a> structure containing controller-specific information about the hardware failure.


## Return Value

This method does not return a value.

## Remarks

The client driver calls <b>UfxDeviceNotifyHardwareFailure</b> when the controller has entered a non-recoverable hardware failure (such as PHY lockup). UFX can try resetting the controller to see if the controller can be recovered. The following example shows the syntax for the call:</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ufxclient.h |
| **Library** |  |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** |  |