---
UID: NF:wdfdevice.WdfDeviceGetDevicePnpState
title: WdfDeviceGetDevicePnpState function
author: windows-driver-content
description: The WdfDeviceGetDevicePnpState method returns the current state of the framework's Plug and Play state machine for a specified device.
old-location: wdf\wdfdevicegetdevicepnpstate.htm
old-project: wdf
ms.assetid: 25936ed9-d213-458f-bbc8-90eedea9ba02
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_8c17c41d-4e8e-499e-83db-92006e4fe08a.xml, WdfDeviceGetDevicePnpState, WdfDeviceGetDevicePnpState method, kmdf.wdfdevicegetdevicepnpstate, wdf.wdfdevicegetdevicepnpstate, wdfdevice/WdfDeviceGetDevicePnpState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceGetDevicePnpState
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceGetDevicePnpState function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceGetDevicePnpState</b> method returns the current state of the framework's Plug and Play state machine for a specified device.

## Syntax

```
WDF_DEVICE_PNP_STATE WdfDeviceGetDevicePnpState(
  WDFDEVICE Device
);
```

## Parameters

`Device`

A handle to a framework device object.


## Return Value

<b>WdfDeviceGetDevicePnpState</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551262">WDF_DEVICE_PNP_STATE</a>-typed enumerator that identifies the current state of the framework's Plug and Play state machine for the specified device.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Most drivers do not need to be aware of the state of the framework's Plug and Play state machine. For more information about the framework's state machines, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.


#### Examples

The following code example obtains the current state of the framework's Plug and Play state machine for a specified device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DEVICE_PNP_STATE state;

state = WdfDeviceGetDevicePnpState(Device);</pre>
</td>
</tr>
</table></span></div>

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546966">WdfDevStateNormalize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545974">WdfDeviceGetDevicePowerPolicyState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545985">WdfDeviceGetDevicePowerState</a>