---
UID: NI.ntdddisk.IOCTL_DISK_UPDATE_DRIVE_SIZE
title: IOCTL_DISK_UPDATE_DRIVE_SIZE
author: windows-driver-content
description: Updates device extension with drive size information for current media.
old-location: storage\ioctl_disk_update_drive_size.htm
old-project: storage
ms.assetid: a12c1082-c3ff-40b8-b756-be320ab98b30
ms.author: windowsdriverdev
ms.date: 12/8/2017
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
req.alt-api: IOCTL_DISK_UPDATE_DRIVE_SIZE
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

# IOCTL_DISK_UPDATE_DRIVE_SIZE IOCTL



## -description

Updates device extension with drive size information for current media.



Updates device extension with drive size information for current media.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer

       Otherwise, the driver returns with an error status of STATUS_BUFFER_TOO_SMALL.

The device driver returns the <a href="storage.disk_geometry">DISK_GEOMETRY</a> structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be &gt;= <b>sizeof</b>(DISK_GEOMETRY). 


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


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
<a href="storage.disk_geometry">DISK_GEOMETRY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_UPDATE_DRIVE_SIZE control code%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

