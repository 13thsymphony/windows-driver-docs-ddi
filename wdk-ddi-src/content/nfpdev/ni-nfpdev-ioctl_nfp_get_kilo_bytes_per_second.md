---
UID: NI:nfpdev.IOCTL_NFP_GET_KILO_BYTES_PER_SECOND
title: IOCTL_NFP_GET_KILO_BYTES_PER_SECOND
author: windows-driver-content
description: A client sends the IOCTL_NFP_GET_KILO_BYTES_PER_SECOND request to any generic handle, one that is non-published and non-subscribed, to the provider device.
old-location: nfpdrivers\ioctl_nfp_get_kilo_bytes_per_second.htm
old-project: nfpdrivers
ms.assetid: 7FAF7D15-1D3A-4F90-BD98-344ECF294E0F
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: _SECURE_ELEMENT_TECH_ROUTING_INFO, *PSECURE_ELEMENT_TECH_ROUTING_INFO, SECURE_ELEMENT_TECH_ROUTING_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: nfpdev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_NFP_GET_KILO_BYTES_PER_SECOND
req.alt-loc: nfpdev.h
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
req.typenames: *PSECURE_ELEMENT_TECH_ROUTING_INFO, SECURE_ELEMENT_TECH_ROUTING_INFO
---

# IOCTL_NFP_GET_KILO_BYTES_PER_SECOND IOCTL



## -description
A client sends the <b>IOCTL_NFP_GET_KILO_BYTES_PER_SECOND</b> request to any generic handle, one that is non-published and non-subscribed, to the provider device. The request is sent in order to determine the approximate best-case transmission speed supported by the provider or its underlying RF technology. This is used to distinguish the difference in one order of magnitude in transmission rate to another.



## -ioctlparameters

### -input-buffer
None


### -input-buffer-length

<text></text>

### -output-buffer
One <b>INT32</b> value that defines the approximate transmission speed supported by the provider or its underlying technology.


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
Each provider implementation can specify an approximate transmission rate. A typical NFC implementation should provide a value of around 50 KB per second.

The following are required actions when using this IOCTL:<ul>
<li>The driver MUST support an approximate transmission rate no smaller than 16 KB per second.</li>
<li>When this IOCTL is received, the driver MUST copy the approximate transmission speed into the output buffer and complete it with STATUS_SUCCESS.</li>
</ul>



## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Nfpdev.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) overall design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfp-design-guide">Near field proximity design guide (Tap and Do, NFP provider model, driver requirements)</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_NFP_GET_KILO_BYTES_PER_SECOND control code%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

