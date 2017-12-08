---
UID: NS.NTDDVOL._DISK_EXTENT
title: _DISK_EXTENT
author: windows-driver-content
description: The DISK_EXTENT structure contains information defining the location and length of a volume extent on a disk.
old-location: storage\disk_extent.htm
old-project: storage
ms.assetid: 74ffdfba-1b80-479d-9637-43222a438fa9
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _DISK_EXTENT, DISK_EXTENT, *PDISK_EXTENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvol.h
req.include-header: Ntddvol.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DISK_EXTENT
req.alt-loc: ntddvol.h
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

# _DISK_EXTENT structure



## -description
The DISK_EXTENT structure contains information defining the location and length of a volume extent on a disk.


## -syntax

````
typedef struct _DISK_EXTENT {
  ULONG         DiskNumber;
  LARGE_INTEGER StartingOffset;
  LARGE_INTEGER ExtentLength;
} DISK_EXTENT, *PDISK_EXTENT;
````


## -struct-fields

### -field DiskNumber

Specifies the number of the disk that contains this extent. This is the same disk number that is used to construct the name of the disk (for example, <i>PhysicalDriveX</i> or <i>HarddiskX</i>, where X is the disk number).

### -field StartingOffset

Specifies the offset, in bytes, from the beginning of the disk.

### -field ExtentLength

Specifies the number of bytes of this extent.

## -remarks


## -requirements
<table>
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
<a href="..\ntddvol\ni-ntddvol-ioctl_volume_get_volume_disk_extents.md">IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS</a>
</dt>
<dt>
<a href="storage.volume_disk_extents">VOLUME_DISK_EXTENTS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_EXTENT structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
