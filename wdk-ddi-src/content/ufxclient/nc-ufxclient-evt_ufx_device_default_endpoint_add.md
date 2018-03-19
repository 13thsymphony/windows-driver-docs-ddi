---
UID: NC:ufxclient.EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD
title: EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD
author: windows-driver-content
description: The client driver's implementation to create a default control endpoint.
old-location: buses\evt_ufx_device_default_endpoint_add.htm
old-project: usbref
ms.assetid: 37AF38A2-F761-4DBC-A7E7-FC4BDA544A31
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD, EvtUfxDeviceDefaultEndpointAdd, EvtUfxDeviceDefaultEndpointAdd callback function [Buses], PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD, PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD callback function pointer [Buses], buses.evt_ufx_device_default_endpoint_add, ufxclient/EvtUfxDeviceDefaultEndpointAdd
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
-	PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---


# EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD callback function
The client driver's implementation to create a default control endpoint.

## Syntax

```
EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD EvtUfxDeviceDefaultEndpointAdd;

void EvtUfxDeviceDefaultEndpointAdd(
  UFXDEVICE ,
  USHORT ,
  PUFXENDPOINT_INIT 
)
{...}
```

## Parameters

`Arg1`



`Arg1`



`Arg1`




## Return Value

This callback function does not return a value.

## Remarks

The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</i> implementation with the USB function class extension (UFX) by calling the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a> method.

To create the endpoint the client driver is expected to initialize the attributes of the endpoint’s transfer and command queues, and then call <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a> to create the endpoint.  After the default control endpoint is created, UFX is ready to process setup packets and other control transfer packets from host.  

The client driver indicates completion of this event by calling the <a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD UfxDevice_EvtDeviceDefaultEndpointAdd;

VOID
UfxDevice_EvtDeviceDefaultEndpointAdd (
    _In_ UFXDEVICE UfxDevice,
    _In_ USHORT MaxPacketSize,
    _Inout_ PUFXENDPOINT_INIT EndpointInit
    )
/*++

Routine Description:

    EvtDeviceDefaultEndpointAdd handler for the UFXDEVICE object.
    Creates UFXENDPOINT object corresponding to the default endpoint of the
    device.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

    MaxPacketSize - Max packet size of the device's default endpoint.

    EndpointInit - Pointer to the Opaque UFXENDPOINT_INIT object

--*/
{
    NTSTATUS Status;
    USB_ENDPOINT_DESCRIPTOR Descriptor;

    PAGED_CODE();

    TraceEntry();

    Descriptor.bDescriptorType = USB_ENDPOINT_DESCRIPTOR_TYPE;
    Descriptor.bEndpointAddress = 0;
    Descriptor.bInterval = 0;
    Descriptor.bLength = sizeof(USB_ENDPOINT_DESCRIPTOR);
    Descriptor.bmAttributes = USB_ENDPOINT_TYPE_CONTROL;
    Descriptor.wMaxPacketSize = MaxPacketSize;

    // #### TODO: Insert code to add the endpoint. 
    // See code example for EVT_UFX_DEVICE_ENDPOINT_ADD ####

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

<a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a>



<a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>