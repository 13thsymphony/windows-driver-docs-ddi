---
UID: NC.ucxusbdevice.EVT_UCX_USBDEVICE_ENDPOINT_ADD
title: EVT_UCX_USBDEVICE_ENDPOINT_ADD
author: windows-driver-content
description: The client driver's implementation that UCX calls to add a new endpoint for a USB device.
old-location: buses\evt_ucx_usbdevice_endpoint_add.htm
old-project: usbref
ms.assetid: 1cbafa33-e957-4865-9d4f-26f12827a941
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _STREAM_INFO, *PSTREAM_INFO, STREAM_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: PEVT_UCX_USBDEVICE_ENDPOINT_ADD
req.alt-loc: ucxusbdevice.h
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

# EVT_UCX_USBDEVICE_ENDPOINT_ADD callback



## -description
The client driver's implementation that UCX calls to add a new endpoint for a USB device.



## -prototype

````
EVT_UCX_USBDEVICE_ENDPOINT_ADD EvtUcxUsbDeviceEndpointAdd;

NTSTATUS EvtUcxUsbDeviceEndpointAdd(
  _In_     UCXCONTROLLER                                 UcxController,
  _In_     UCXUSBDEVICE                                  UcxUsbDevice,
  _In_     PUSB_ENDPOINT_DESCRIPTOR                      UsbEndpointDescriptor,
  _In_     ULONG                                         UsbEndpointDescriptorBufferLength,
  _In_opt_ PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR SuperSpeedEndpointCompanionDescriptor,
  _In_     PUCXENDPOINT_INIT                             UcxEndpointInit
)
{ ... }

typedef EVT_UCX_USBDEVICE_ENDPOINT_ADD PEVT_UCX_USBDEVICE_ENDPOINT_ADD;
````


## -parameters

### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="buses._ucxcontrollercreate">UcxControllerCreate</a> method.


### -param UcxUsbDevice [in]

A handle to a UCX object that represents the USB device.


### -param UsbEndpointDescriptor [in]

A pointer to a location containing a USB descriptor for the endpoint being created.


### -param UsbEndpointDescriptorBufferLength [in]

Length in bytes of the descriptor.


### -param SuperSpeedEndpointCompanionDescriptor [in, optional]

An additional descriptor for a super speed port. This parameter is optional and may be <b>NULL</b>.


### -param UcxEndpointInit [in]

A pointer to an opaque structure containing initialization
    information.  Callbacks for the endpoint object are associated with this
    structure.  This structure is managed by UCX.


## -returns
If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.


## -remarks
The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="buses._ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.

The callback function calls <a href="buses._ucxendpointcreate">UcxEndpointCreate</a> to create a new endpoint object and register endpoint object callback functions.

Then, the callback  function typically creates a WDF queue associated with the endpoint
    object.   The  queue does not receive any requests until the class extension
    starts it.


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucxusbdevice.h (include Ucxclass.h)</dt>
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
<a href="buses._ucxdefaultendpointinitseteventcallbacks">UcxDefaultEndpointInitSetEventCallbacks</a>
</dt>
<dt>
<a href="buses._ucxendpointcreate">UcxEndpointCreate</a>
</dt>
<dt>
<a href="buses._ucxusbdevicecreate">UcxUsbDeviceCreate</a>
</dt>
<dt>
<a href="wdf.wdf_io_queue_config_init">WDF_IO_QUEUE_CONFIG_INIT</a>
</dt>
<dt>
<a href="wdf.wdfioqueuecreate">WdfIoQueueCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_USBDEVICE_ENDPOINT_ADD callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

