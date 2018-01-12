---
UID: NI:usbioctl.IOCTL_USB_HCD_DISABLE_PORT
title: IOCTL_USB_HCD_DISABLE_PORT
author: windows-driver-content
description: The IOCTL_USB_HCD_DISABLE_PORT IOCTL has been deprecated. Do not use.
old-location: buses\ioctl_usb_hcd_disable_port.htm
old-project: usbref
ms.assetid: c0ae41be-1b37-4410-8e7a-611a66c599c1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USB_HUB_TYPE, USB_HUB_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows Server 2003, Windows XP, and Windows 2000, but it is not available on Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_USB_HCD_DISABLE_PORT
req.alt-loc: Usbioctl.h
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
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_HCD_DISABLE_PORT IOCTL



## -description
The <b>IOCTL_USB_HCD_DISABLE_PORT</b> IOCTL has been deprecated. Do not use.



## -ioctlparameters

### -input-buffer

<text></text>

### -input-buffer-length

<text></text>

### -output-buffer

<text></text>

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available on Microsoft Windows Server 2003, Windows XP, and Windows 2000, but it is not available on Windows Vista.

</td>
</tr>
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