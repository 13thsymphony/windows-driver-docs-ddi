---
UID: NS.NTDDDISK._CREATE_DISK_MBR
title: _CREATE_DISK_MBR
author: windows-driver-content
description: The CREATE_DISK_MBR structure is used with the IOCTL IOCTL_DISK_CREATE_DISK to initialize a disk with an empty MBR partition table.
old-location: storage\create_disk_mbr.htm
old-project: storage
ms.assetid: afc0e705-ae98-486b-82d3-4f21fca89e70
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _CREATE_DISK_MBR, CREATE_DISK_MBR, *PCREATE_DISK_MBR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CREATE_DISK_MBR
req.alt-loc: ntdddisk.h
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

# _CREATE_DISK_MBR structure



## -description
The CREATE_DISK_MBR structure is used with the IOCTL <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_create_disk.md">IOCTL_DISK_CREATE_DISK</a> to initialize a disk with an empty MBR partition table.


## -syntax

````
typedef struct _CREATE_DISK_MBR {
  ULONG Signature;
} CREATE_DISK_MBR, *PCREATE_DISK_MBR;
````


## -struct-fields

### -field Signature

Specifies the disk signature value, which uniquely identifies the disk.

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
<a href="storage.create_disk">CREATE_DISK</a>
</dt>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_create_disk.md">IOCTL_DISK_CREATE_DISK</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CREATE_DISK_MBR structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
