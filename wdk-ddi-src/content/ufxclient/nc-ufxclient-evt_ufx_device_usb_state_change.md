---
UID: NC:ufxclient.EVT_UFX_DEVICE_USB_STATE_CHANGE
title: EVT_UFX_DEVICE_USB_STATE_CHANGE
author: windows-driver-content
description: The client driver's implementation to update the state of the USB device.
old-location: buses\evt_ufx_device_usb_state_change.htm
old-project: usbref
ms.assetid: 81D4F3C5-7412-4148-A5B4-0C56DD9ADB35
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UFX_DEVICE_USB_STATE_CHANGE, EvtUfxDeviceUsbStateChange, EvtUfxDeviceUsbStateChange callback function [Buses], PFN_UFX_DEVICE_USB_STATE_CHANGE, PFN_UFX_DEVICE_USB_STATE_CHANGE callback function pointer [Buses], buses.evt_ufx_device_usb_state_change, ufxclient/EvtUfxDeviceUsbStateChange
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ufxclient.h
api_name:
-	PFN_UFX_DEVICE_USB_STATE_CHANGE
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---


# EVT_UFX_DEVICE_USB_STATE_CHANGE callback function
The client driver's implementation to update the state of the USB device.

## Syntax

```
EVT_UFX_DEVICE_USB_STATE_CHANGE EvtUfxDeviceUsbStateChange;

void EvtUfxDeviceUsbStateChange(
  UFXDEVICE ,
  USBFN_DEVICE_STATE 
)
{...}
```

## Parameters

`Arg1`



`Arg1`




## Return Value

This callback function does not return a value.

## Remarks

The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_USB_STATE_CHANGE</i> implementation with the USB function class extension (UFX) by calling the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a> method.

UFX invokes this event callback to inform the client driver about the new state of the device.

The client driver indicates completion of this event by calling the <a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UFX_DEVICE_USB_STATE_CHANGE UfxDevice_EvtDeviceUsbStateChange;

VOID
UfxDevice_EvtDeviceUsbStateChange (
    _In_ UFXDEVICE UfxDevice,
    _In_ USBFN_DEVICE_STATE NewState
)
/*++

Routine Description:

    EvtDeviceUsbStateChange handler for the UFXDEVICE object.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

    NewState - The new device state.

--*/
{
    NTSTATUS Status;
    PUFXDEVICE_CONTEXT Context;
    PCONTROLLER_CONTEXT ControllerContext;
    ULONG EpIndex;
    USBFN_DEVICE_STATE OldState;
 
    PAGED_CODE();

    TraceEntry();

    Context = UfxDeviceGetContext(UfxDevice);
    ControllerContext = DeviceGetControllerContext(Context-&gt;FdoWdfDevice);
    OldState = Context-&gt;UsbState;

    TraceInformation("New STATE: %d", NewState);

    Status = UfxDeviceStopOrResumeIdle(UfxDevice, NewState, Context-&gt;UsbPort);
    LOG_NT_MSG(Status, "Failed to stop or resume idle");

    WdfWaitLockAcquire(ControllerContext-&gt;InitializeDefaultEndpointLock, NULL);
    if (ControllerContext-&gt;InitializeDefaultEndpoint == TRUE) {
        //
        // Reset endpoint 0. This is the last part of soft reset, which was postponed
        // until now, since we need to make sure EP0 is created by UFX.
        //
        DeviceInitializeDefaultEndpoint(Context-&gt;FdoWdfDevice);
        ControllerContext-&gt;InitializeDefaultEndpoint = FALSE;
    }
    WdfWaitLockRelease(ControllerContext-&gt;InitializeDefaultEndpointLock);

    if (NewState == UsbfnDeviceStateConfigured &amp;&amp; OldState != UsbfnDeviceStateSuspended) {

        for (EpIndex = 1; EpIndex &lt; WdfCollectionGetCount(Context-&gt;Endpoints); EpIndex++) {
            UfxEndpointConfigure(WdfCollectionGetItem(Context-&gt;Endpoints, EpIndex));
        }

        // 
        // #### TODO: Insert code to allow the controller to accept U1/U2, if supported ####
        //
       
    }


    if (NewState == UsbfnDeviceStateDetached) {
        KeSetEvent(&amp;ControllerContext-&gt;DetachEvent,
                   IO_NO_INCREMENT,
                   FALSE);
    }

    UfxDeviceEventComplete(UfxDevice, STATUS_SUCCESS);
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

<a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a>



<a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>