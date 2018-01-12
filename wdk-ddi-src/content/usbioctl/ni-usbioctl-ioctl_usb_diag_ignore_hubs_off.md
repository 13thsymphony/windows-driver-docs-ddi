---
UID: NI:usbioctl.IOCTL_USB_DIAG_IGNORE_HUBS_OFF
title: IOCTL_USB_DIAG_IGNORE_HUBS_OFF
author: windows-driver-content
description: The IOCTL_USB_DIAG_IGNORE_HUBS_OFF I/O control has been deprecated. Do not use.
old-location: buses\ioctl_usb_diag_ignore_hubs_off.htm
old-project: usbref
ms.assetid: e81b096b-273e-48ca-acff-3e4df5a607f4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USB_HUB_TYPE, USB_HUB_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Supported on Microsoft Windows 2000 only.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_USB_DIAG_IGNORE_HUBS_OFF
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

# IOCTL_USB_DIAG_IGNORE_HUBS_OFF IOCTL



## -description

The <b>IOCTL_USB_DIAG_IGNORE_HUBS_OFF</b> I/O control has been deprecated. Do not use.  



The <b>IOCTL_USB_DIAG_IGNORE_HUBS_OFF</b> I/O control has been deprecated. Do not use.  



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
Supported on Microsoft Windows 2000 only.

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