---
UID: NF.ntddk.IoReadPartitionTableEx
title: IoReadPartitionTableEx
author: windows-driver-content
description: The IoReadPartitionTableEx routine reads a list of partitions on a disk having a specified sector size and creates an entry in the partition list for each recognized partition.
old-location: storage\ioreadpartitiontableex.htm
old-project: storage
ms.assetid: 1aa8665a-1674-4fca-b5c6-d8d25166ca29
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: IoReadPartitionTableEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoReadPartitionTableEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.iface: 
---

# IoReadPartitionTableEx function



## -description
<p>The <b>IoReadPartitionTableEx</b> routine reads a list of partitions on a disk having a specified sector size and creates an entry in the partition list for each recognized partition. </p>


## -syntax

````
NTSTATUS IoReadPartitionTableEx(
  _In_  PDEVICE_OBJECT                      DeviceObject,
  _Out_ struct _DRIVE_LAYOUT_INFORMATION_EX **PartitionBuffer
);
````


## -parameters
<dl>

### -param <i>DeviceObject</i> [in]

<dd>
<p>Pointer to the device object for the disk whose partitions are to be read.</p>
</dd>

### -param <i>PartitionBuffer</i> [out]

<dd>
<p>Pointer to an uninitialized address. If successful, <b>IoReadPartitionTableEx</b> allocates the memory for this buffer from nonpaged pool and returns the drive layout information in it.</p>
</dd>
</dl>

## -returns
<p>This routine returns a value of STATUS_SUCCESS if at least one sector table was read. Otherwise, it returns an error status value and sets the pointer at <i>PartitionBuffer</i> to <b>NULL</b>.</p>

## -remarks
<p><b>IoReadPartitionTableEx</b> must only be used by disk drivers. Other drivers should use the <a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-get-drive-layout-ex.md">IOCTL_DISK_GET_DRIVE_LAYOUT_EX</a> disk I/O request instead.</p>

<p><b>IoReadPartitionTableEx</b> is able to read partition table information from GUID Partition Table (GPT) disks as well as legacy Master Boot Record (MBR) disks. Disk device drivers call this routine during driver initialization.</p>

<p>It is the responsibility of the caller to deallocate the <i>PartitionBuffer</i> that was allocated by this routine with <b>ExFreePool</b>.</p>

<p>Note that disk drivers also return and set partition information in response to IRP_MJ_DEVICE_CONTROL requests with the following I/O control codes:</p>

<p>
<dl>
<dt>IOCTL_DISK_GET_PARTITION_INFO_EX</dt>
<dt>IOCTL_DISK_SET_PARTITION_INFO_EX</dt>
<dt>IOCTL_DISK_GET_DRIVE_LAYOUT_EX</dt>
<dt>IOCTL_DISK_SET_DRIVE_LAYOUT_EX</dt>
<dt>IOCTL_DISK_GET_DRIVE_GEOMETRY</dt>
</dl>
</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
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
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntdddisk\ns-ntdddisk--drive-layout-information-ex.md">DRIVE_LAYOUT_INFORMATION_EX</a>
</dt>
<dt>
<a href="..\ntdddisk\ns-ntdddisk--partition-information-ex.md">PARTITION_INFORMATION_EX</a>
</dt>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-get-partition-info-ex.md">IOCTL_DISK_GET_PARTITION_INFO_EX</a>
</dt>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-set-partition-info-ex.md">IOCTL_DISK_SET_PARTITION_INFO_EX</a>
</dt>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-get-drive-layout-ex.md">IOCTL_DISK_GET_DRIVE_LAYOUT_EX</a>
</dt>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-set-drive-layout-ex.md">IOCTL_DISK_SET_DRIVE_LAYOUT_EX</a>
</dt>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-get-drive-geometry.md">IOCTL_DISK_GET_DRIVE_GEOMETRY</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iosetpartitioninformation.md">IoSetPartitionInformation</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iowritepartitiontableex.md">IoWritePartitionTableEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IoReadPartitionTableEx routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
