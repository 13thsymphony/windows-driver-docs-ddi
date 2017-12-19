---
UID: NE.udecxusbdevice._UDECX_ENDPOINT_TYPE
title: _UDECX_ENDPOINT_TYPE
author: windows-driver-content
description: Defines values for endpoint types supported by a virtual USB device.
old-location: buses\udecx_endpoint_type.htm
old-project: UsbRef
ms.assetid: EFA5DDC0-9E6B-450E-B191-1DA9FBAC269C
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _UDECX_ENDPOINT_TYPE, PUDECX_ENDPOINT_TYPE, UDECX_ENDPOINT_TYPE, *PUDECX_ENDPOINT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UDECX_ENDPOINT_TYPE
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
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# _UDECX_ENDPOINT_TYPE enumeration



## -description
Defines values for endpoint types supported by a virtual USB device.



## -syntax

````
typedef enum _UDECX_ENDPOINT_TYPE { 
  UdecxEndpointTypeInvalid  = 0,
  UdecxEndpointTypeSimple   = ,
  UdecxEndpointTypeDynamic  = 
} UDECX_ENDPOINT_TYPE;
````


## -enum-fields

### -field UdecxEndpointTypeInvalid

The endpoint is not of a valid type.


### -field UdecxEndpointTypeSimple

The endpoint is defined in the first (and only) interface setting of the interface. That device has only one configuration. The client driver creates all endpoints before the device is detected. 


### -field UdecxEndpointTypeDynamic

The endpoint is dynamically created in the client driver's implementation of the <a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure.md">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a> callback.


## -remarks


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="buses.udecxusbdeviceinitsetendpointstype">UdecxUsbDeviceInitSetEndpointsType</a>
</dt>
<dt>
<a href="buses.usb_endpoints_and_their_pipes">USB endpoints</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UDECX_ENDPOINT_TYPE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

