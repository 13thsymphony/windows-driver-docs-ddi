---
UID: NS.ntdddisk._DRIVE_LAYOUT_INFORMATION
title: DRIVE_LAYOUT_INFORMATION
author: windows-driver-content
description: The DRIVE_LAYOUT_INFORMATION structure is obsolete and is provided only to support existing drivers.
old-location: storage\drive_layout_information.htm
old-project: storage
ms.assetid: 980cd307-9048-4054-be8e-967d15862a14
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: DRIVE_LAYOUT_INFORMATION, DRIVE_LAYOUT_INFORMATION, *PDRIVE_LAYOUT_INFORMATION
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
req.alt-api: DRIVE_LAYOUT_INFORMATION
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

# DRIVE_LAYOUT_INFORMATION structure



## -description
<p>The DRIVE_LAYOUT_INFORMATION structure is obsolete and is provided only to support existing drivers. New drivers must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a>. </p>
<p>The DRIVE_LAYOUT_INFORMATION structure is used to report information about a disk drive and its partitions. It is also used to write new drive layout information to the disk. </p>


## -syntax

````
typedef struct _DRIVE_LAYOUT_INFORMATION {
  ULONG                 PartitionCount;
  ULONG                 Signature;
  PARTITION_INFORMATION PartitionEntry[1];
} DRIVE_LAYOUT_INFORMATION, *PDRIVE_LAYOUT_INFORMATION;
````


## -struct-fields
<dl>

### -field <b>PartitionCount</b>

<dd>
<p>Contains the number of partitions on the drive. </p>
</dd>

### -field <b>Signature</b>

<dd>
<p>Contains the disk signature.</p>
</dd>

### -field <b>PartitionEntry</b>

<dd>
<p>Contains a variable-length array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563751">PARTITION_INFORMATION</a> structures, one for each partition on the drive. </p>
</dd>
</dl>

## -remarks
<p>In Windows 2000 and later operating systems, disk drivers should use structures <a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563754">PARTITION_INFORMATION_EX</a> along with routines <b>IoReadPartitionTableEx</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561461">IoSetPartitionInformationEx</a> to read and alter partition information on the disk. </p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560373">IOCTL_DISK_GET_PARTITION_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560361">IOCTL_DISK_GET_DRIVE_LAYOUT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560408">IOCTL_DISK_SET_DRIVE_LAYOUT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561452">IoReadPartitionTable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561454">IoReadPartitionTableEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561456">IoSetPartitionInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561464">IoWritePartitionTable</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DRIVE_LAYOUT_INFORMATION structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
