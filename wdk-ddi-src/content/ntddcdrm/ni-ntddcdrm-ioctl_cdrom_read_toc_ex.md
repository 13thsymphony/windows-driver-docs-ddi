---
UID: NI:ntddcdrm.IOCTL_CDROM_READ_TOC_EX
title: IOCTL_CDROM_READ_TOC_EX
author: windows-driver-content
description: Queries the target device for the table of contents (TOC), the program memory area (PMA), and the absolute time in pregroove (ATIP).
old-location: storage\ioctl_cdrom_read_toc_ex.htm
old-project: storage
ms.assetid: 279df233-9164-4c80-b31f-1d4cdc1073fa
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _WRITE_ROTATION, *PWRITE_ROTATION, WRITE_ROTATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows XP and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_CDROM_READ_TOC_EX
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
req.typenames: *PWRITE_ROTATION, WRITE_ROTATION
---

# IOCTL_CDROM_READ_TOC_EX IOCTL



## -description

Queries the target device for the table of contents (TOC), the program memory area (PMA), and the absolute time in pregroove (ATIP). If the media is not a CD-ROM and does not support a TOC, this IOCTL returns information similar to that of a CD-ROM TOC. This is required for compatibility with some legacy initiator environments. 



Queries the target device for the table of contents (TOC), the program memory area (PMA), and the absolute time in pregroove (ATIP). If the media is not a CD-ROM and does not support a TOC, this IOCTL returns information similar to that of a CD-ROM TOC. This is required for compatibility with some legacy initiator environments. 



## -ioctlparameters

### -input-buffer
<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a buffer of type <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_read_toc_ex.md">CDROM_READ_TOC_EX</a> whose contents indicate what information should be retrieved from the target device. 

<b>Parameters.Read.Length</b> in the I/O stack location indicates the size, in bytes, of the information to be retrieved from the target device. 


### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the input buffer, which must be &gt;= <b>sizeof</b>(CDROM_READ_TOC_EX).


### -output-buffer
The driver returns the query data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the output buffer, which must be &gt;= MINIMUM_CDROM_READ_TOC_EX_SIZE.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INSUFFICIENT_RESOURCES.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows XP and later operating systems.

</td>
</tr>
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

## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_read_toc_ex.md">CDROM_READ_TOC_EX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_READ_TOC_EX control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

