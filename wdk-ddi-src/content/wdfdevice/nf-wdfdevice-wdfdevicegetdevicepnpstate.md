---
UID : NF:wdfdevice.WdfDeviceGetDevicePnpState
title : WdfDeviceGetDevicePnpState function
author : windows-driver-content
description : The WdfDeviceGetDevicePnpState method returns the current state of the framework's Plug and Play state machine for a specified device.
old-location : wdf\wdfdevicegetdevicepnpstate.htm
old-project : wdf
ms.assetid : 25936ed9-d213-458f-bbc8-90eedea9ba02
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfDeviceGetDevicePnpState, wdf.wdfdevicegetdevicepnpstate, kmdf.wdfdevicegetdevicepnpstate, PFN_WDFDEVICEGETDEVICEPNPSTATE, wdfdevice/WdfDeviceGetDevicePnpState, WdfDeviceGetDevicePnpState method, DFDeviceObjectGeneralRef_8c17c41d-4e8e-499e-83db-92006e4fe08a.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfdevice.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_STATE_NOTIFICATION_TYPE
req.product : Windows 10 or later.
---


# WdfDeviceGetDevicePnpState function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceGetDevicePnpState</b> method returns the current state of the framework's Plug and Play state machine for a specified device.

## Syntax

````
WDF_DEVICE_PNP_STATE WdfDeviceGetDevicePnpState(
  _In_ WDFDEVICE Device
);
````

## Parameters

`Device`

A handle to a framework device object.


## Return Value

<b>WdfDeviceGetDevicePnpState</b> returns a <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_pnp_state.md">WDF_DEVICE_PNP_STATE</a>-typed enumerator that identifies the current state of the framework's Plug and Play state machine for the specified device.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Most drivers do not need to be aware of the state of the framework's Plug and Play state machine. For more information about the framework's state machines, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevstatenormalize.md">WdfDevStateNormalize</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicepowerstate.md">WdfDeviceGetDevicePowerState</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicepowerpolicystate.md">WdfDeviceGetDevicePowerPolicyState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceGetDevicePnpState method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>