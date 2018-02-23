---
UID: NC:ufxclient.EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL
title: EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL
author: windows-driver-content
description: The client driver's implementation to initiate remote wake-up on the function controller.
old-location: buses\evt_ufx_device_remote_wakeup_signal.htm
old-project: UsbRef
ms.assetid: A1250501-DC33-4AA8-8AD7-9938ECAC8AFB
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: buses.evt_ufx_device_remote_wakeup_signal, EvtUfxDeviceRemoteWakeupSignal callback function [Buses], EvtUfxDeviceRemoteWakeupSignal, EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL, EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL, ufxclient/EvtUfxDeviceRemoteWakeupSignal, PFN_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL callback function pointer [Buses], PFN_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ufxclient.h
apiname:
-	PFN_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL
product: Windows
targetos: Windows
req.typenames: "*PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT"
req.product: Windows 10 or later.
---


# EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL function
The client driver's implementation to initiate remote wake-up on the function controller.

## Syntax

```
EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL EvtUfxDeviceRemoteWakeupSignal;

void EvtUfxDeviceRemoteWakeupSignal(

)
{...}
```

## Parameters

This function has no parameters.

## Return Value

This callback function does not return a value.

## Remarks

The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL</i> implementation with the USB function class extension (UFX) by calling the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a> method.

The client driver indicates completion of this event by calling the <a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL UfxDevice_EvtDeviceRemoteWakeupSignal;

VOID
UfxDevice_EvtDeviceRemoteWakeupSignal (
    _In_ UFXDEVICE UfxDevice
    )
/*++
Routine Description:

    Signals Remote Wakeup to the Host by issuing a link state change command.
    It acquires and releases the power reference to ensure a valid power state
    before accessing the device.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

--*/
{
    NTSTATUS Status;
    PUFXDEVICE_CONTEXT DeviceContext;

    PAGED_CODE();

    TraceEntry();

    DeviceContext = UfxDeviceGetContext(UfxDevice);

    //
    // Stop Idle to ensure the device is in working state
    //

    Status = WdfDeviceStopIdle(DeviceContext-&gt;FdoWdfDevice, TRUE);
    if (!NT_SUCCESS(Status)) {
        TraceError("Failed to stop idle %!STATUS!", Status);
        goto End;
    }

    //
    // Issue a Link State Change Request.
    //

    //
    // #### TODO: Insert code to issue a link state change on the controller ####
    //

    WdfDeviceResumeIdle(DeviceContext-&gt;FdoWdfDevice);

End:
    UfxDeviceEventComplete(UfxDevice, Status);
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
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>



<a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>