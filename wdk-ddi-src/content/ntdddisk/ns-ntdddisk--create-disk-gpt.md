---
UID: NS.ntdddisk._CREATE_DISK_GPT
title: CREATE_DISK_GPT
author: windows-driver-content
description: The CREATE_DISK_GPT structure is used with the IOCTL IOCTL_DISK_CREATE_DISK to initialize a disk with an empty GPT partition table.
old-location: storage\create_disk_gpt.htm
old-project: storage
ms.assetid: 24ae7329-064f-43bf-8c1d-8aad9fdf2254
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: CREATE_DISK_GPT, CREATE_DISK_GPT, *PCREATE_DISK_GPT
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
req.alt-api: CREATE_DISK_GPT
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
req.iface: 
---

# CREATE_DISK_GPT structure



## -description
<p>The CREATE_DISK_GPT structure is used with the IOCTL <a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-create-disk.md">IOCTL_DISK_CREATE_DISK</a> to initialize a disk with an empty GPT partition table.</p>


## -syntax

````
typedef struct _CREATE_DISK_GPT {
  GUID  DiskId;
  ULONG MaxPartitionCount;
} CREATE_DISK_GPT, *PCREATE_DISK_GPT;
````


## -struct-fields
<dl>

### -field DiskId

<dd>
<p>Specifies the GUID that uniquely identifies the disk.</p>
</dd>

### -field MaxPartitionCount

<dd>
<p>Specifies the maximum number of partitions allowed on the disk.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\ntdddisk\ns-ntdddisk--create-disk.md">CREATE_DISK</a>
</dt>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-create-disk.md">IOCTL_DISK_CREATE_DISK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CREATE_DISK_GPT structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
