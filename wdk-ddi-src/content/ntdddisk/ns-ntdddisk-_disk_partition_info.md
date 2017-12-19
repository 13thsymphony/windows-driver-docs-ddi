---
UID: NS.NTDDDISK._DISK_PARTITION_INFO
title: _DISK_PARTITION_INFO
author: windows-driver-content
description: The DISK_PARTITION_INFO structure is used to report information about the disk's partition table.
old-location: storage\disk_partition_info.htm
old-project: storage
ms.assetid: 14df0604-39cd-4743-a051-894d63f4417c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DISK_PARTITION_INFO, *PDISK_PARTITION_INFO, PDISK_PARTITION_INFO, DISK_PARTITION_INFO
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
req.alt-api: DISK_PARTITION_INFO
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

# _DISK_PARTITION_INFO structure



## -description
The <b>DISK_PARTITION_INFO</b> structure is used to report information about the disk's partition table. 



## -syntax

````
typedef struct _DISK_PARTITION_INFO {
  ULONG           SizeOfPartitionInfo;
  PARTITION_STYLE PartitionStyle;
  union {
    struct {
      ULONG Signature;
      ULONG CheckSum;
    } Mbr;
    struct {
      GUID DiskId;
    } Gpt;
  };
} DISK_PARTITION_INFO, *PDISK_PARTITION_INFO;
````


## -struct-fields

### -field SizeOfPartitionInfo

Size of this structure in bytes. Set to <b>sizeof</b>(DISK_PARTITION_INFO).


### -field PartitionStyle

Takes a <a href="storage.partition_style">PARTITION_STYLE</a> enumerated value that specifies the type of partition table the disk contains.


### -field Mbr

If <b>PartitionStyle</b> == MBR


### -field Signature

Specifies the signature value, which uniquely identifies the disk. The <b>Mbr</b> member of the union is used to specify the disk signature data for a disk formatted with a Master Boot Record (MBR) format partition table. Any other value indicates that the partition is not a boot partition. This member is valid when <b>PartitionStyle</b> is <b>PARTITION_STYLE_MBR</b>. 


### -field CheckSum

Specifies the checksum for the master boot record. The <b>Mbr</b> member of the union is used to specify the disk signature data for a disk formatted with a Master Boot Record (MBR) format partition table. This member is valid when <b>PartitionStyle</b> is <b>PARTITION_STYLE_MBR</b>. 

</dd>
</dl>

### -field Gpt

If <b>PartitionStyle</b> == GPT


### -field DiskId

Specifies the GUID that uniquely identifies the disk. The <b>Gpt</b> member of the union is used to specify the disk signature data for a disk that is formatted with a GUID Partition Table (GPT) format partition table. This member is valid when <b>PartitionStyle</b> is <b>PARTITION_STYLE_GPT</b>. The GUID data type is described on the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a> reference page.

</dd>
</dl>

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
<a href="storage.disk_geometry_ex">DISK_GEOMETRY_EX</a>
</dt>
<dt>
<a href="storage.partition_style">PARTITION_STYLE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_PARTITION_INFO structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

