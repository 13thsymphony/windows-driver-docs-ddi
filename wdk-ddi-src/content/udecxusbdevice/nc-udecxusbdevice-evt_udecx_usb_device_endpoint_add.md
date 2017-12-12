---
UID: NC.udecxusbdevice.EVT_UDECX_USB_DEVICE_ENDPOINT_ADD
title: EVT_UDECX_USB_DEVICE_ENDPOINT_ADD
author: windows-driver-content
description: The USB device emulation class extension (UdeCx) invokes this callback function to request the client driver to create a dynamic endpoint on the virtual USB device.
old-location: buses\evt_udecx_usb_device_endpoint_add.htm
old-project: usbref
ms.assetid: 82E17C75-BE81-4263-AC04-D3C93505917D
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UdecxUrbSetBytesCompleted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.alt-api: EvtUsbDeviceEndpointAdd
req.alt-loc: UdecxUsbDevice.h
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
req.product: Windows 10 or later.
---

# EVT_UDECX_USB_DEVICE_ENDPOINT_ADD callback



## -description
The USB device emulation class extension (UdeCx) invokes this callback function to request the client driver to create a dynamic endpoint on the virtual USB device.



## -prototype

````
EVT_UDECX_USB_DEVICE_ENDPOINT_ADD EvtUsbDeviceEndpointAdd;

NTSTATUS EvtUsbDeviceEndpointAdd(
  _In_ UDECXUSBDEVICE                                     UdecxUsbDevice,
  _In_ PUDECX_USB_ENDPOINT_INIT_AND_METADATA              EndpointToCreate
)
{ ... }
````


## -parameters

### -param UdecxUsbDevice [in]

A handle to the UDE device object for which the client driver creates an endpoint. The driver created this object in a previous call to <a href="buses.udecxusbdevicecreate">UdecxUsbDeviceCreate</a>.


### -param EndpointToCreate [in]

A pointer to a <a href="buses.udecx_usb_endpoint_init_and_metadata">UDECX_USB_ENDPOINT_INIT_AND_METADATA</a>             structure that contains the endpoint descriptor.


## -returns
If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.


## -remarks
The client driver registered this callback function in a previous call to <a href="buses.udecxusbdeviceinitsetstatechangecallbacks">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.

In the implementation, the client driver is expected to create the endpoint by calling <a href="buses.udecxusbendpointcreate">UdecxUsbEndpointCreate</a> by using the initialization parameters (<b>UDECXUSBENDPOINT_INIT</b>) passed by the class extension in the <a href="buses.udecx_usb_endpoint_init_and_metadata">UDECX_USB_ENDPOINT_INIT_AND_METADATA</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.15

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>UdecxUsbDevice.h (include Udecx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.udecxusbendpointcreate">UdecxUsbEndpointCreate</a>
</dt>
<dt>
<a href="buses.usb_emulated_device__ude__architecture">Architecture: USB Device Emulation (UDE)</a>
</dt>
<dt>
<a href="buses.writing_a_ude_client_driver">Write a UDE client driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UDECX_USB_DEVICE_ENDPOINT_ADD callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

