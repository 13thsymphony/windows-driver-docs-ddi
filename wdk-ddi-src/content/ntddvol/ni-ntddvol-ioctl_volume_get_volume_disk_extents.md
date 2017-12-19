---
UID: NI.ntddvol.IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS
title: IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS
author: windows-driver-content
description: Returns the physical location(s) of a volume on one or more disks.
old-location: storage\ioctl_volume_get_volume_disk_extents.htm
old-project: storage
ms.assetid: d831ea36-16ee-4723-95b1-f9903106b7c0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _VIDEO_WIN32K_CALLBACKS_PARAMS, PVIDEO_WIN32K_CALLBACKS_PARAMS, VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvol.h
req.include-header: Ntddvol.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows 2000 for volumes on fixed disks, but not for volumes on removable media. Available for use with removable media in Microsoft Windows 2000 SP4 and Windows XP SP1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS
req.alt-loc: Ntddvol.h
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

# IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS IOCTL



## -description

Returns the physical location(s) of a volume on one or more disks. Extents are initially stored in the order in which they are created, but remirroring, splitting, or breaking a mirror, or actions taken during disaster recovery, can affect the order of disk extents.



Returns the physical location(s) of a volume on one or more disks. Extents are initially stored in the order in which they are created, but remirroring, splitting, or breaking a mirror, or actions taken during disaster recovery, can affect the order of disk extents.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The driver returns a VOLUME_DISK_EXTENTS structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be at least <b>sizeof</b>(VOLUME_DISK_EXTENTS). 


### -output-buffer-length
The length of a VOLUME_DISK_EXTENTS structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The driver sets <b>Irp-&gt;IoStatus.Information</b> and the <b>Status</b> field as follows:

If the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is &lt; <b>sizeof</b>(VOLUME_DISK_EXTENTS), the driver sets <b>Irp-&gt;IoStatus.Information</b> to zero and returns STATUS_INVALID_PARAMETER.

If the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is at least <b>sizeof</b>(VOLUME_DISK_EXTENTS) but too small for all data to be returned, the driver sets <b>Irp-&gt;IoStatus.Information</b> to <b>sizeof</b>(VOLUME_DISK_EXTENTS) and sets <b>Status</b> to STATUS_BUFFER_OVERFLOW.

If the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is large enough for all data to be returned, the driver sets <b>Irp-&gt;IoStatus.Information</b> to <b>sizeof</b>(VOLUME_DISK_EXTENTS) + ((NumberOfDiskExtents - 1) * <b>sizeof</b>(DISK_EXTENT)) and sets <b>Status</b> to STATUS_SUCCESS. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows 2000 for volumes on fixed disks, but not for volumes on removable media. Available for use with removable media in Microsoft Windows 2000 SP4 and Windows XP SP1.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddvol.h (include Ntddvol.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.volume_disk_extents">VOLUME_DISK_EXTENTS</a>
</dt>
<dt>
<a href="storage.disk_extent">DISK_EXTENT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS control code%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

