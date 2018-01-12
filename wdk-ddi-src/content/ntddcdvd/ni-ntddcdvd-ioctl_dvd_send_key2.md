---
UID: NI:ntddcdvd.IOCTL_DVD_SEND_KEY2
title: IOCTL_DVD_SEND_KEY2
author: windows-driver-content
description: Sends the specified key to a DVD device -to complete the related step in an authentication sequence. The IOCTL_DVD_SEND_KEY2 request has write access to the device and can send a broader range of key types than IOCTL_DVD_SEND_KEY.
old-location: storage\ioctl_dvd_send_key2.htm
old-project: storage
ms.assetid: 58b9c2a5-cd29-4c62-b5ae-39911821e3b7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_DVD_SEND_KEY2
req.alt-loc: Ntddcdvd.h
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
req.typenames: *PDVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT
---

# IOCTL_DVD_SEND_KEY2 IOCTL



## -description

Sends the specified key to a DVD device -to complete the related step in an authentication sequence. The IOCTL_DVD_SEND_KEY2 request has write access to the device and can send a broader range of key types than <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_send_key.md">IOCTL_DVD_SEND_KEY</a>. 



Sends the specified key to a DVD device -to complete the related step in an authentication sequence. The IOCTL_DVD_SEND_KEY2 request has write access to the device and can send a broader range of key types than <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_send_key.md">IOCTL_DVD_SEND_KEY</a>. 



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copy_protect_key.md">DVD_COPY_PROTECT_KEY</a> structure that indicates the session ID, key type, and key to be sent to the device.


### -input-buffer-length
Length of a <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copy_protect_key.md">DVD_COPY_PROTECT_KEY</a>.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddcdvd.h (include Ntddcdvd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copy_protect_key.md">DVD_COPY_PROTECT_KEY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DVD_SEND_KEY2 control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

