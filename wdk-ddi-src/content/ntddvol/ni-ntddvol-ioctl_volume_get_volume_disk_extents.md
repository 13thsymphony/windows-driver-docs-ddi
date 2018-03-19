---
UID: NI:ntddvol.IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS
title: IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS
author: windows-driver-content
description: Returns the physical location(s) of a volume on one or more disks.
old-location: storage\ioctl_volume_get_volume_disk_extents.htm
old-project: storage
ms.assetid: d831ea36-16ee-4723-95b1-f9903106b7c0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS, IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS control code [Storage Devices], k307_8f02f744-6892-4e3f-9b23-158370e6a1e9.xml, ntddvol/IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS, storage.ioctl_volume_get_volume_disk_extents
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddvol.h
api_name:
-	IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS
product: Windows
targetos: Windows
req.typenames: VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS
---

# IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS IOCTL
Returns the physical location(s) of a volume on one or more disks. Extents are initially stored in the order in which they are created, but remirroring, splitting, or breaking a mirror, or actions taken during disaster recovery, can affect the order of disk extents.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The driver returns a VOLUME_DISK_EXTENTS structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be at least <b>sizeof</b>(VOLUME_DISK_EXTENTS).

### Output Buffer Length
The length of a VOLUME_DISK_EXTENTS structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The driver sets <b>Irp-&gt;IoStatus.Information</b> and the <b>Status</b> field as follows:

<ul>
<li>
If the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is &lt; <b>sizeof</b>(VOLUME_DISK_EXTENTS), the driver sets <b>Irp-&gt;IoStatus.Information</b> to zero and returns STATUS_INVALID_PARAMETER.

</li>
<li>
If the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is at least <b>sizeof</b>(VOLUME_DISK_EXTENTS) but too small for all data to be returned, the driver sets <b>Irp-&gt;IoStatus.Information</b> to <b>sizeof</b>(VOLUME_DISK_EXTENTS) and sets <b>Status</b> to STATUS_BUFFER_OVERFLOW.

</li>
<li>
If the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is large enough for all data to be returned, the driver sets <b>Irp-&gt;IoStatus.Information</b> to <b>sizeof</b>(VOLUME_DISK_EXTENTS) + ((NumberOfDiskExtents - 1) * <b>sizeof</b>(DISK_EXTENT)) and sets <b>Status</b> to STATUS_SUCCESS. 

</li>
</ul>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows 2000 for volumes on fixed disks, but not for volumes on removable media. Available for use with removable media in Microsoft Windows 2000 SP4 and Windows XP SP1. Available in Microsoft Windows 2000 for volumes on fixed disks, but not for volumes on removable media. Available for use with removable media in Microsoft Windows 2000 SP4 and Windows XP SP1. |
| **Header** | ntddvol.h (include Ntddvol.h) |

## See Also

<a href="..\ntddvol\ns-ntddvol-_volume_disk_extents.md">VOLUME_DISK_EXTENTS</a>



<a href="..\ntddvol\ns-ntddvol-_disk_extent.md">DISK_EXTENT</a>