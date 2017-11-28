---
UID: NS.usbioctl._USB_HUB_CAPABILITIES_EX
title: USB_HUB_CAPABILITIES_EX
author: windows-driver-content
description: The USB_HUB_CAPABILITIES_EX structure is used with the IOCTL_USB_GET_HUB_CAPABILITIES I/O control request to retrieve the capabilities of a particular USB hub.
old-location: buses\usb_hub_capabilities_ex.htm
old-project: usbref
ms.assetid: deb8d710-6137-4f69-8fde-00d46cdb6f4f
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: USB_HUB_CAPABILITIES_EX, USB_HUB_CAPABILITIES_EX, *PUSB_HUB_CAPABILITIES_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_HUB_CAPABILITIES_EX
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

# USB_HUB_CAPABILITIES_EX structure



## -description
<p>The <b>USB_HUB_CAPABILITIES_EX</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537312">IOCTL_USB_GET_HUB_CAPABILITIES</a> I/O control request to retrieve the capabilities of a particular USB hub.</p>


## -syntax

````
typedef struct _USB_HUB_CAPABILITIES_EX {
  USB_HUB_CAP_FLAGS CapabilityFlags;
} USB_HUB_CAPABILITIES_EX, *PUSB_HUB_CAPABILITIES_EX;
````


## -struct-fields
<dl>

### -field <b>CapabilityFlags</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff539330">USB_HUB_CAP_FLAGS</a> structure that reports the hub capabilities.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later operating systems. </p>
</td>
</tr>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537312">IOCTL_USB_GET_HUB_CAPABILITIES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539330">USB_HUB_CAP_FLAGS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_HUB_CAPABILITIES_EX structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
