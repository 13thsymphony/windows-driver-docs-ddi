---
UID: NC.ufxclient.EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD
title: EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD
author: windows-driver-content
description: The client driver's implementation to create a default control endpoint.
old-location: buses\evt_ufx_device_default_endpoint_add.htm
old-project: usbref
ms.assetid: 37AF38A2-F761-4DBC-A7E7-FC4BDA544A31
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
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
req.alt-api: PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD
req.alt-loc: Ufxclient.h
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

# EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD callback



## -description
The client driver's implementation to create a default control endpoint.



## -prototype

````
EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD EvtUfxDeviceDefaultEndpointAdd;

void EvtUfxDeviceDefaultEndpointAdd(
  _In_    UFXDEVICE         UfxDevice,
  _In_    USHORT            MaxPacketSize,
  _Inout_ PUFXENDPOINT_INIT EndpointInit
)
{ ... }

typedef EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD;
````


## -parameters

### -param UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="buses.ufxdevicecreate">UfxDeviceCreate</a>.


### -param MaxPacketSize [in]

The default maximum packet size that can be sent from or to this endpoint.


### -param EndpointInit [in, out]

A pointer to an  UFXENDPOINT_INIT opaque structure that contains the endpoint descriptor required  to create an endpoint object.


## -returns
This callback function does not return a value.


## -remarks
The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</i> implementation with the USB function class extension (UFX) by calling the <a href="buses.ufxdevicecreate">UfxDeviceCreate</a> method.

To create the endpoint the client driver is expected to initialize the attributes of the endpoint’s transfer and command queues, and then call <a href="buses.ufxendpointcreate">UfxEndpointCreate</a> to create the endpoint.  After the default control endpoint is created, UFX is ready to process setup packets and other control transfer packets from host.  

The client driver indicates completion of this event by calling the <a href="buses.ufxdeviceeventcomplete">UfxDeviceEventComplete</a> method.


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
<dt>Ufxclient.h</dt>
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
<a href="buses.ufxdevicecreate">UfxDeviceCreate</a>
</dt>
<dt>
<a href="buses.ufxdeviceeventcomplete">UfxDeviceEventComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

