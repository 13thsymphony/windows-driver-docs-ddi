---
UID: NI.ntdddisk.IOCTL_DISK_SET_DRIVE_LAYOUT
title: IOCTL_DISK_SET_DRIVE_LAYOUT
author: windows-driver-content
description: Repartitions a disk as specified. (Floppy drivers need not handle this request.).
old-location: storage\ioctl_disk_set_drive_layout.htm
old-project: storage
ms.assetid: d6b0682a-bce2-40d3-a69b-cf676c21d253
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DETECTION_TYPE, DETECTION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_DISK_SET_DRIVE_LAYOUT
req.alt-loc: Ntdddisk.h
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

# IOCTL_DISK_SET_DRIVE_LAYOUT IOCTL



## -description

Repartitions a disk as specified. (Floppy drivers need not handle this request.)



Repartitions a disk as specified. (Floppy drivers need not handle this request.)



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="storage.drive_layout_information">DRIVE_LAYOUT_INFORMATION</a> values to be set. 


### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(DRIVE_LAYOUT_INFORMATION).


### -output-buffer
Returns updated <a href="storage.drive_layout_information">DRIVE_LAYOUT_INFORMATION</a>, possibly with modified partition numbers, to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length
Length of a <a href="storage.drive_layout_information">DRIVE_LAYOUT_INFORMATION</a>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the size, in bytes, of the returned information. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_PARAMETER, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, or STATUS_BUFFER_TOO_SMALL.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntdddisk.h (include Ntdddisk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.drive_layout_information">DRIVE_LAYOUT_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_SET_DRIVE_LAYOUT control code%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

