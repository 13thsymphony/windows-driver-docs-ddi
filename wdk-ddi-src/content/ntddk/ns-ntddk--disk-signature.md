---
UID: NS.ntddk._DISK_SIGNATURE
title: DISK_SIGNATURE
author: windows-driver-content
description: DISK_SIGNATURE contains the disk signature information for a disk's partition table.
old-location: storage\disk_signature.htm
old-project: storage
ms.assetid: f3fdb436-53b6-4fb3-8746-1f852f7d928a
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: DISK_SIGNATURE, DISK_SIGNATURE, *PDISK_SIGNATURE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: This structure is only available on Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DISK_SIGNATURE
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# DISK_SIGNATURE structure



## -description
<p>DISK_SIGNATURE contains the disk signature information for a disk's partition table.</p>


## -syntax

````
typedef struct _DISK_SIGNATURE {
  ULONG PartitionStyle;
  union {
    struct {
      ULONG Signature;
      ULONG CheckSum;
    } Mbr;
    struct {
      GUID DiskId;
    } Gpt;
  };
} DISK_SIGNATURE, *PDISK_SIGNATURE;
````


## -struct-fields
<dl>

### -field <b>PartitionStyle</b>

<dd>
<p>Specifies the type of partition.  See <a href="storage.partition_style">PARTITION_STYLE</a> for a description of the possible values.</p>
</dd>

### -field <b>Mbr</b>

<dd>
<dl>

### -field <b>Signature</b>

<dd>
<p>Specifies the signature value, which uniquely identifies the disk. The <b>Mbr</b> member of the union is used to specify the disk signature data for a disk formatted with a Master Boot Record (MBR) format partition table. This member is valid when <b>PartitionStyle</b> is PARTITION_STYLE_MBR. </p>
</dd>

### -field <b>CheckSum</b>

<dd>
<p>Specifies the checksum for the master boot record. The <b>Mbr</b> member of the union is used to specify the disk signature data for a disk formatted with a Master Boot Record (MBR) format partition table. This member is valid when <b>PartitionStyle</b> is PARTITION_STYLE_MBR. </p>
</dd>
</dl>
</dd>

### -field <b>Gpt</b>

<dd>
<dl>

### -field <b>DiskId</b>

<dd>
<p>Specifies the GUID that uniquely identifies the disk. The <b>Gpt</b> member of the union is used to specify the disk signature data for a disk that is formatted with a GUID Partition Table (GPT) format partition table. The GUID data type is described on the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a> reference page. This member is valid when <b>PartitionStyle</b> is PARTITION_STYLE_GPT. </p>
</dd>
</dl>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>This structure is only available on Windows XP and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-ioreaddisksignature.md">IoReadDiskSignature</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_SIGNATURE structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
