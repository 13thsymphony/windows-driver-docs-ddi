---
UID: NS.usbioctl._USB_NODE_CONNECTION_NAME
title: USB_NODE_CONNECTION_NAME
author: windows-driver-content
description: The USB_NODE_CONNECTION_NAME structure is used with the IOCTL_USB_GET_NODE_CONNECTION_NAME I/O control request to retrieve the symbolic link of the downstream hub that is attached to the port.
old-location: buses\usb_node_connection_name.htm
old-project: usbref
ms.assetid: f38248fb-b2aa-417a-9d9b-36ff069bf78f
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: USB_NODE_CONNECTION_NAME, USB_NODE_CONNECTION_NAME, *PUSB_NODE_CONNECTION_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_NODE_CONNECTION_NAME
req.alt-loc: usbioctl.h
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
req.iface: 
req.product: Windows 10 or later.
---

# USB_NODE_CONNECTION_NAME structure



## -description
<p>The <b>USB_NODE_CONNECTION_NAME</b> structure is used with the <a href="..\usbioctl\ni-usbioctl-ioctl-usb-get-node-connection-name.md">IOCTL_USB_GET_NODE_CONNECTION_NAME</a> I/O control request to retrieve the symbolic link of the downstream hub that is attached to the port.</p>


## -syntax

````
typedef struct _USB_NODE_CONNECTION_NAME {
  ULONG ConnectionIndex;
  ULONG ActualLength;
  WCHAR NodeName[1];
} USB_NODE_CONNECTION_NAME, *PUSB_NODE_CONNECTION_NAME;
````


## -struct-fields
<dl>

### -field ConnectionIndex

<dd>
<p>A value that is greater than or equal to 1 that specifies the number of the port to which the hub is attached.</p>
</dd>

### -field ActualLength

<dd>
<p>The length, in bytes, of the attached hub's symbolic link.</p>
</dd>

### -field NodeName

<dd>
<p>A Unicode symbolic link for the downstream hub that is attached to the port that is indicated by <b>ConnectionIndex</b>. If there is no attached device, the attached device does not have a symbolic link, or if the device is not a hub, <b>NodeName</b>[0] will contain a value of UNICODE_NULL.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Usbioctl.h (include Usbioctl.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usbioctl\ni-usbioctl-ioctl-usb-get-node-connection-name.md">IOCTL_USB_GET_NODE_CONNECTION_NAME</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_NODE_CONNECTION_NAME structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
