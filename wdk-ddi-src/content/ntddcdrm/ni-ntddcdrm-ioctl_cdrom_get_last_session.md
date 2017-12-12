---
UID: NI.ntddcdrm.IOCTL_CDROM_GET_LAST_SESSION
title: IOCTL_CDROM_GET_LAST_SESSION
author: windows-driver-content
description: Queries the device for the first complete session number, the last complete session number, and the last complete session starting address.
old-location: storage\ioctl_cdrom_get_last_session.htm
old-project: storage
ms.assetid: a05da124-f486-4658-87d8-6c1b423694b3
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WRITE_ROTATION, WRITE_ROTATION, *PWRITE_ROTATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_CDROM_GET_LAST_SESSION
req.alt-loc: ntddcdrm.h
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
---

# IOCTL_CDROM_GET_LAST_SESSION IOCTL



## -description
Queries the device for the first complete session number, the last complete session number, and the last complete session starting address. This request is the same as an <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a> request with a format of CDROM_READ_TOC_EX_FORMAT_SESSION. For more information on the CDROM_READ_TOC_EX_FORMAT_SESSION format, see the description of the <b>Format</b> member of the <a href="storage.cdrom_read_toc_ex">CDROM_READ_TOC_EX</a> structure.

On output, if the value in the <b>FirstCompleteSession</b> member of <a href="storage.cdrom_toc_session_data">CDROM_TOC_SESSION_DATA</a> is  the same as the value in the <b>LastCompleteSession</b> member, the disc is not multisession. 



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The driver returns the query data in a <a href="storage.cdrom_toc_session_data">CDROM_TOC_SESSION_DATA</a> structure at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length
Length of a <a href="storage.cdrom_toc_session_data">CDROM_TOC_SESSION_DATA</a> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INSUFFICIENT_RESOURCES.


## -remarks
TBD


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>