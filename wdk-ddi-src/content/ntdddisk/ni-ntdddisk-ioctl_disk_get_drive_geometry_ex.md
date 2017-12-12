---
UID: NI.ntdddisk.IOCTL_DISK_GET_DRIVE_GEOMETRY_EX
title: IOCTL_DISK_GET_DRIVE_GEOMETRY_EX
author: windows-driver-content
description: Returns information about the physical disk's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).The difference between IOCTL_DISK_GET_DRIVE_GEOMETRY_EX and the older IOCTL_DISK_GET_DRIVE_GEOMETRY request is that IOCTL_DISK_GET_DRIVE_GEOMETRY_EX can retrieve information from both Master Boot Record (MBR) and GUID Partition Table (GPT)-type partitioned media, whereas IOCTL_DISK_GET_DRIVE_GEOMETRY can only read MBR-style media.
old-location: storage\ioctl_disk_get_drive_geometry_ex.htm
old-project: storage
ms.assetid: c0cf6b73-3283-4a58-845a-79f3b078db46
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DETECTION_TYPE, DETECTION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_DISK_GET_DRIVE_GEOMETRY_EX
req.alt-loc: Ntdddisk.h
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

# IOCTL_DISK_GET_DRIVE_GEOMETRY_EX IOCTL



## -description

Returns information about the physical disk's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).

The difference between IOCTL_DISK_GET_DRIVE_GEOMETRY_EX and the older <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_geometry.md">IOCTL_DISK_GET_DRIVE_GEOMETRY</a> request is that IOCTL_DISK_GET_DRIVE_GEOMETRY_EX can retrieve information from both Master Boot Record (MBR) and GUID Partition Table (GPT)-type partitioned media, whereas IOCTL_DISK_GET_DRIVE_GEOMETRY can only read MBR-style media. 



Returns information about the physical disk's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).

The difference between IOCTL_DISK_GET_DRIVE_GEOMETRY_EX and the older <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_geometry.md">IOCTL_DISK_GET_DRIVE_GEOMETRY</a> request is that IOCTL_DISK_GET_DRIVE_GEOMETRY_EX can retrieve information from both Master Boot Record (MBR) and GUID Partition Table (GPT)-type partitioned media, whereas IOCTL_DISK_GET_DRIVE_GEOMETRY can only read MBR-style media. 



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The driver returns the <a href="storage.disk_geometry_ex">DISK_GEOMETRY_EX</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The size of the output buffer may not be the same size as the input buffer.


### -output-buffer-length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least (<b>sizeof</b>(DISK_GEOMETRY) + <b>sizeof</b>(LARGE_INTEGER)) and up to (<b>sizeof</b>(DISK_GEOMETRY) + <b>sizeof</b>(LARGE_INTEGER) + <b>sizeof</b>(DISK_PARTITION_INFO) + <b>sizeof</b>(DISK_DETECTION_INFO)).


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the size, in bytes, of the returned data. 

The <b>Status</b> field returns one of the following values:


## -remarks
Only callers above Partmgr.sys may call this IOCTL as it contains disk partition information. 

This IOCTL uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff560357">IOCTL_DISK_GET_DRIVE_GEOMETRY</a> to get the <a href="storage.disk_geometry">DISK_GEOMETRY</a> structure and <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_length_info.md">IOCTL_DISK_GET_LENGTH_INFO</a> to get the  <a href="storage.get_length_information">GET_LENGTH_INFORMATION</a> structure. Both of these IOCTL's are supported for use at the disk.sys level. 


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