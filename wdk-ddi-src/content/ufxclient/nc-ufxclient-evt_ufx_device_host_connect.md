---
UID: NC:ufxclient.EVT_UFX_DEVICE_HOST_CONNECT
title: EVT_UFX_DEVICE_HOST_CONNECT
author: windows-driver-content
description: The client driver's implementation to initiate connection with the host.
old-location: buses\evt_ufx_device_host_connect.htm
old-project: usbref
ms.assetid: 8F38C4EC-08BD-4CEF-97AB-B282ECC19627
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
product: Windows
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

The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_HOST_CONNECT</i> implementation with the USB function class extension (UFX) by calling the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a> method.

The client driver must not initiate connection with the host until UFX invokes this  event callback. The client driver shall indicate completion of this event by calling the <a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a> method. 


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

<a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a>



<a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UFX_DEVICE_HOST_CONNECT callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>