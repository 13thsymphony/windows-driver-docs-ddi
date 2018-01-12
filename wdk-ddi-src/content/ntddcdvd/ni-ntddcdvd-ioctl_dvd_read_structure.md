---
UID: NI:ntddcdvd.IOCTL_DVD_READ_STRUCTURE
title: IOCTL_DVD_READ_STRUCTURE
author: windows-driver-content
description: Returns information about a DVD disc, such as a layer descriptor, copyright information, or manufacturer-specific information.
old-location: storage\ioctl_dvd_read_structure.htm
old-project: storage
ms.assetid: 64cf4d53-5d03-43bc-b295-37ecf67b4d2a
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
req.alt-api: IOCTL_DVD_READ_STRUCTURE
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

# IOCTL_DVD_READ_STRUCTURE IOCTL



## -description

Returns information about a DVD disc, such as a layer descriptor, copyright information, or manufacturer-specific information.



Returns information about a DVD disc, such as a layer descriptor, copyright information, or manufacturer-specific information.



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddcdvd\ns-ntddcdvd-dvd_read_structure.md">DVD_READ_STRUCTURE</a> structure that indicates the session ID and type of information to return. 


### -input-buffer-length
Length of a <a href="..\ntddcdvd\ns-ntddcdvd-dvd_read_structure.md">DVD_READ_STRUCTURE</a>.


### -output-buffer
The driver returns the disc information in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof(</b><i>Descriptor</i><b>)</b> where <i>Descriptor</i> is <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_layer_descriptor.md">DVD_LAYER_DESCRIPTOR</a>, <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copyright_descriptor.md">DVD_COPYRIGHT_DESCRIPTOR</a>, <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_disk_key_descriptor.md">DVD_DISK_KEY_DESCRIPTOR</a>, <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_bca_descriptor.md">DVD_BCA_DESCRIPTOR</a>, or <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_manufacturer_descriptor.md">DVD_MANUFACTURER_DESCRIPTOR</a>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.


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
<a href="..\ntddcdvd\ns-ntddcdvd-dvd_read_structure.md">DVD_READ_STRUCTURE</a>
</dt>
<dt>
<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_layer_descriptor.md">DVD_LAYER_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copyright_descriptor.md">DVD_COPYRIGHT_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_disk_key_descriptor.md">DVD_DISK_KEY_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_bca_descriptor.md">DVD_BCA_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_manufacturer_descriptor.md">DVD_MANUFACTURER_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DVD_READ_STRUCTURE control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

