---
UID: NS.USBIOCTL._USB_HUB_NAME
title: _USB_HUB_NAME
author: windows-driver-content
description: The USB_HUB_NAME structure stores the hub's symbolic device name.
old-location: buses\usb_hub_name.htm
old-project: UsbRef
ms.assetid: c213d811-a690-41b4-bed1-ec9890e8be46
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _USB_HUB_NAME, PUSB_HUB_NAME, USB_HUB_NAME, *PUSB_HUB_NAME
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
req.alt-api: USB_HUB_NAME
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

# _USB_HUB_NAME structure



## -description
The <b>USB_HUB_NAME</b> structure stores the hub's symbolic device name.



## -syntax

````
typedef struct _USB_HUB_NAME {
  ULONG ActualLength;
  WCHAR HubName[1];
} USB_HUB_NAME, *PUSB_HUB_NAME;
````


## -struct-fields

### -field ActualLength

The size of the Unicode string pointed to by <b>HubName</b>.  The <b>ActualLength</b> value indicates the length of the string and not the entire structure.


### -field HubName

A NULL-terminated Unicode string that contains the hub's symbolic device name.


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
<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_get_controller_name.md">IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USB_HUB_NAME structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

