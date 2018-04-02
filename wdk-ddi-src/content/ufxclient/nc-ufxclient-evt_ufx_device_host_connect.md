---
UID: NC:ufxclient.EVT_UFX_DEVICE_HOST_CONNECT
title: EVT_UFX_DEVICE_HOST_CONNECT
author: windows-driver-content
description: The client driver's implementation to initiate connection with the host.
old-location: buses\evt_ufx_device_host_connect.htm
old-project: usbref
ms.assetid: 8F38C4EC-08BD-4CEF-97AB-B282ECC19627
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EVT_UFX_DEVICE_HOST_CONNECT, EvtUfxDeviceHostConnect, EvtUfxDeviceHostConnect callback function [Buses], PFN_UFX_DEVICE_HOST_CONNECT, PFN_UFX_DEVICE_HOST_CONNECT callback function pointer [Buses], buses.evt_ufx_device_host_connect, ufxclient/EvtUfxDeviceHostConnect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ufxclient.h
api_name:
-	PFN_UFX_DEVICE_HOST_CONNECT
product:
- Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---


# EVT_UFX_DEVICE_HOST_CONNECT callback function
The client driver's implementation to initiate connection with the host.

## Syntax

```
EVT_UFX_DEVICE_HOST_CONNECT EvtUfxDeviceHostConnect;

void EvtUfxDeviceHostConnect(

)
{...}
```

## Parameters

This function has no parameters.

## Return Value

This callback function does not return a value.

## Remarks

The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_HOST_CONNECT</i> implementation with the USB function class extension (UFX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a> method.

The client driver must not initiate connection with the host until UFX invokes this  event callback. The client driver shall indicate completion of this event by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a> method. 


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UFX_DEVICE_HOST_CONNECT UfxDevice_EvtDeviceHostConnect;

VOID
UfxDevice_EvtDeviceHostConnect (
    _In_ UFXDEVICE UfxDevice
    )
/*++

Routine Description:

    EvtDeviceHostConnect callback handler for UFXDEVICE object.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

--*/
{
    PCONTROLLER_CONTEXT ControllerContext;
    PUFXDEVICE_CONTEXT DeviceContext;
    BOOLEAN EventComplete;

    TraceEntry();

    DeviceContext = UfxDeviceGetContext(UfxDevice);
    ControllerContext = DeviceGetControllerContext(DeviceContext-&gt;FdoWdfDevice);

    EventComplete = TRUE;

    WdfSpinLockAcquire(ControllerContext-&gt;DpcLock);

    //
    // #### TODO: Insert code to set the run state on the controller ####
    //

    WdfSpinLockRelease(ControllerContext-&gt;DpcLock);

    if (EventComplete) {
        UfxDeviceEventComplete(UfxDevice, STATUS_SUCCESS);
    }

    TraceExit();
}
</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ufxclient.h |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a>