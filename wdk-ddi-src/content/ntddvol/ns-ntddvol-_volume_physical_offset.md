---
UID: NS.NTDDVOL._VOLUME_PHYSICAL_OFFSET
title: _VOLUME_PHYSICAL_OFFSET
author: windows-driver-content
description: The VOLUME_PHYSICAL_OFFSET structure contains a physical offset into a volume and its accompanying physical disk number and is used with IOCTL_VOLUME_PHYSICAL_TO_LOGICAL and IOCTL_VOLUME_LOGICAL_TO_PHYSICAL to request a logical offset equivalent of a physical offset or a physical offset equivalent of a logical offset, respectively.
old-location: storage\volume_physical_offset.htm
old-project: storage
ms.assetid: 068875e3-4229-4f15-9533-f740239ac873
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _VOLUME_PHYSICAL_OFFSET, VOLUME_PHYSICAL_OFFSET, *PVOLUME_PHYSICAL_OFFSET
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
req.alt-api: VOLUME_PHYSICAL_OFFSET
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

# _VOLUME_PHYSICAL_OFFSET structure



## -description
The VOLUME_PHYSICAL_OFFSET structure contains a physical offset into a volume and its accompanying physical disk number and is used with <a href="..\ntddvol\ni-ntddvol-ioctl_volume_physical_to_logical.md">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a> and <a href="..\ntddvol\ni-ntddvol-ioctl_volume_logical_to_physical.md">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a> to request a logical offset equivalent of a physical offset or a physical offset equivalent of a logical offset, respectively.



## -syntax

````
typedef struct _VOLUME_PHYSICAL_OFFSET {
  ULONG    DiskNumber;
  LONGLONG Offset;
} VOLUME_PHYSICAL_OFFSET, *PVOLUME_PHYSICAL_OFFSET;
````


## -struct-fields

### -field DiskNumber

Contains the number of the physical disk. 


### -field Offset

Contains the physical offset in bytes of the data on the disk. 


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
<a href="..\ntddvol\ni-ntddvol-ioctl_volume_logical_to_physical.md">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a>
</dt>
<dt>
<a href="..\ntddvol\ni-ntddvol-ioctl_volume_physical_to_logical.md">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20VOLUME_PHYSICAL_OFFSET structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

