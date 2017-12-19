---
UID: NS.USBIOCTL._USB_NODE_CONNECTION_ATTRIBUTES
title: _USB_NODE_CONNECTION_ATTRIBUTES
author: windows-driver-content
description: The USB_NODE_CONNECTION_ATTRIBUTES structure is used with the IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES I/O control request to retrieve the attributes of a connection.
old-location: buses\usb_node_connection_attributes.htm
old-project: UsbRef
ms.assetid: 893dc1f2-785e-434e-88c7-9bbf2f1c4ad6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _USB_NODE_CONNECTION_ATTRIBUTES, PUSB_NODE_CONNECTION_ATTRIBUTES, *PUSB_NODE_CONNECTION_ATTRIBUTES, USB_NODE_CONNECTION_ATTRIBUTES
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
req.alt-api: USB_NODE_CONNECTION_ATTRIBUTES
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
req.product: Windows 10 or later.
---

# _USB_NODE_CONNECTION_ATTRIBUTES structure



## -description
The <b>USB_NODE_CONNECTION_ATTRIBUTES</b> structure is used with the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_attributes.md">IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</a> I/O control request to retrieve the attributes of a connection.



## -syntax

````
typedef struct _USB_NODE_CONNECTION_ATTRIBUTES {
  ULONG                 ConnectionIndex;
  USB_CONNECTION_STATUS ConnectionStatus;
  ULONG                 PortAttributes;
} USB_NODE_CONNECTION_ATTRIBUTES, *PUSB_NODE_CONNECTION_ATTRIBUTES;
````


## -struct-fields

### -field ConnectionIndex

On input to the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_attributes.md">IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</a> I/O control request, this member contains the number of the port.


### -field ConnectionStatus

On output from the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_attributes.md">IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</a> I/O control request, this member contains a <a href="buses.usb_connection_status">USB_CONNECTION_STATUS</a> enumerator that indicates the connection status.


### -field PortAttributes

On output from the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_attributes.md">IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</a> I/O control request, this member contains the Microsoft-extended port attributes.

For Windows Vista, Windows Server 2008, and Windows 7 the Microsoft-extended port attributes field will always be zero.  

For Windows XP and Windows Server 2003, <b>PortAttributes</b> value might be set to the  Microsoft-extended port attributes, USB_PORTATTR_NO_OVERCURRENT_UI. This attribute indicates that no user-visible interface will be displayed when overcurrent occurs on the port.
	



## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_attributes.md">IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</a>
</dt>
<dt>
<a href="buses.usb_connection_status">USB_CONNECTION_STATUS</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USB_NODE_CONNECTION_ATTRIBUTES structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

