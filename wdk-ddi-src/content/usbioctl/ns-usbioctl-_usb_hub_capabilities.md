---
UID: NS.USBIOCTL._USB_HUB_CAPABILITIES
title: _USB_HUB_CAPABILITIES
author: windows-driver-content
description: The USB_HUB_CAPABILITIES structure has been deprecated. Use USB_HUB_CAPABILITIES_EX instead.
old-location: buses\usb_hub_capabilities.htm
old-project: usbref
ms.assetid: a87f747f-474d-401d-9757-0820680e5c8e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USB_HUB_CAPABILITIES, USB_HUB_CAPABILITIES, *PUSB_HUB_CAPABILITIES
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
req.alt-api: USB_HUB_CAPABILITIES
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

# _USB_HUB_CAPABILITIES structure



## -description
The <b>USB_HUB_CAPABILITIES</b> structure has been deprecated. Use <a href="buses.usb_hub_capabilities_ex">USB_HUB_CAPABILITIES_EX</a> instead.



## -syntax

````
typedef struct _USB_HUB_CAPABILITIES {
  ULONG HubIs2xCapable  :1;
} USB_HUB_CAPABILITIES, *PUSB_HUB_CAPABILITIES;
````


## -struct-fields

### -field HubIs2xCapable

If <b>TRUE</b>, the hub is capable of running at high speed.


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
<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_capabilities.md">IOCTL_USB_GET_HUB_CAPABILITIES</a>
</dt>
<dt>
<a href="buses.usb_hub_cap_flags">USB_HUB_CAP_FLAGS</a>
</dt>
<dt>
<a href="buses.usb_hub_capabilities_ex">USB_HUB_CAPABILITIES_EX</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_HUB_CAPABILITIES structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

