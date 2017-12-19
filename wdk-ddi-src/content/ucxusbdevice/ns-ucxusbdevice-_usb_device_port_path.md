---
UID: NS.UCXUSBDEVICE._USB_DEVICE_PORT_PATH
title: _USB_DEVICE_PORT_PATH
author: windows-driver-content
description: Contains the port path of a USB device.
old-location: buses\_usb_device_port_path.htm
old-project: UsbRef
ms.assetid: 75C7DB08-F831-43ED-8373-F3F4C7AF89E8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _USB_DEVICE_PORT_PATH, PUSB_DEVICE_PORT_PATH, USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_DEVICE_PORT_PATH
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
req.irql: 
req.product: Windows 10 or later.
---

# _USB_DEVICE_PORT_PATH structure



## -description
Contains the port path of a USB device.



## -syntax

````
typedef struct _USB_DEVICE_PORT_PATH {
  ULONG Size;
  ULONG PortPathDepth;
  ULONG TTHubDepth;
  ULONG PortPath[MAX_USB_DEVICE_DEPTH];
} USB_DEVICE_PORT_PATH, *P_USB_DEVICE_PORT_PATH;
````


## -struct-fields

### -field Size

The size in bytes of this structure.


### -field PortPathDepth

The depth of path in the USB topology tree, consisting of host controller, hubs, and devices.


### -field TTHubDepth

The depth of path in the USB topology tree from a TT hub. 


### -field PortPath

The index of connected USB port on the hub.


## -remarks


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="buses._ucxusbdevice_info">UCXUSBDEVICE_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USB_DEVICE_PORT_PATH structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

