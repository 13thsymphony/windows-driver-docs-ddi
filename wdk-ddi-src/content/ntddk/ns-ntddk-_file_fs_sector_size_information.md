---
UID: NS.NTDDK._FILE_FS_SECTOR_SIZE_INFORMATION
title: _FILE_FS_SECTOR_SIZE_INFORMATION
author: windows-driver-content
description: The FILE_FS_SECTOR_SIZE_INFORMATION structure is used to query physical and logical sector size information for a file system volume.
old-location: ifsk\file_fs_sector_size_information.htm
old-project: ifsk
ms.assetid: 24DEEDC7-B339-44DD-BF48-3BD59520EB8D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _FILE_FS_SECTOR_SIZE_INFORMATION, PFILE_FS_SECTOR_SIZE_INFORMATION, *PFILE_FS_SECTOR_SIZE_INFORMATION, FILE_FS_SECTOR_SIZE_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_FS_SECTOR_SIZE_INFORMATION
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
---

# _FILE_FS_SECTOR_SIZE_INFORMATION structure



## -description
The <b>FILE_FS_SECTOR_SIZE_INFORMATION</b> structure is used to query physical and logical sector size information for a file system volume. 



## -syntax

````
typedef struct _FILE_FS_SECTOR_SIZE_INFORMATION {
  ULONG LogicalBytesPerSector;
  ULONG PhysicalBytesPerSectorForAtomicity;
  ULONG PhysicalBytesPerSectorForPerformance;
  ULONG FileSystemEffectivePhysicalBytesPerSectorForAtomicity;
  ULONG Flags;
  ULONG ByteOffsetForSectorAlignment;
  ULONG ByteOffsetForPartitionAlignment;
} FILE_FS_SECTOR_SIZE_INFORMATION, *PFILE_FS_SECTOR_SIZE_INFORMATION;
````


## -struct-fields

### -field LogicalBytesPerSector

Logical bytes per sector  reported by physical storage. This is the same value as the block size for used for Logical Block Addressing (LBA).


### -field PhysicalBytesPerSectorForAtomicity

Actual bytes per sector reported by physical storage used for an atomic write.


### -field PhysicalBytesPerSectorForPerformance

Bytes per sector reported by physical storage for best performance.


### -field FileSystemEffectivePhysicalBytesPerSectorForAtomicity

The portion of <b>PhysicalBytesPerSectorForAtomicity</b> considered as the physical sector size by the file system.


### -field Flags

Flags for sector alignment and performance capabilities. This value is a bitwise OR combination of the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field SSINFO_FLAGS_ALIGNED_DEVICE

</td>
<td width="60%">
Logical sectors of the storage device are aligned to physical sector boundaries.

</td>
</tr>
<tr>

### -field SSINFO_FLAGS_PARTITION_ALIGNED_ON_DEVICE

</td>
<td width="60%">
The partition is aligned to physical sector boundaries on the storage device.

</td>
</tr>
<tr>

### -field SSINFO_FLAGS_NO_SEEK_PENALTY

</td>
<td width="60%">
The storage device has no seek penalty.

</td>
</tr>
<tr>

### -field SSINFO_FLAGS_PARTITION_ALIGNED_ON_DEVICE

</td>
<td width="60%">
The storage device supports the TRIM operation.

</td>
</tr>
</table>
 


### -field ByteOffsetForSectorAlignment

The offset, in bytes, of the beginning of the first logical sector within the first physical sector. This member is set to <b>SSINFO_OFFSET_UNKNOWN</b> if proper device information is not available to calculate the value.


### -field ByteOffsetForPartitionAlignment

The offset value, in bytes, used to align the partition to a physical sector boundary. This member is set to <b>SSINFO_OFFSET_UNKNOWN</b> if proper device information is not available to calculate the value.


## -remarks
This information can be queried in either of the following ways: 

Call <a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a> or <a href="kernel.zwqueryvolumeinformationfile">ZwQueryVolumeInformationFile</a>, passing <b>FileFsSectorSizeInformation</b> as the value of <i>FileInformationClass</i> and passing a caller-allocated, <b>FILE_FS_SECTOR_SIZE_INFORMATION</b>-structured buffer as the value of <i>FileInformation</i>. 

Create an IRP with major function code <a href="ifsk.irp_mj_query_volume_information">IRP_MJ_QUERY_VOLUME_INFORMATION</a>. 

Call <a href="ifsk.fsrtlgetsectorsizeinformation">FsRtlGetSectorSizeInformation</a> with a pointer to a <b>FILE_FS_SECTOR_SIZE_INFORMATION</b>-structured buffer. The  <b>FileSystemEffectivePhysicalBytesPerSectorForAtomicity</b> member will not have a value initialized by  the file system when this structure is returned from <b>FsRtlGetSectorSizeInformation</b>. A file system driver will typically call this function and then set its own value for  <b>FileSystemEffectivePhysicalBytesPerSectorForAtomicity</b>.

No specific access rights are required to query this information. Thus this information is available as long as the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a> or <a href="kernel.zwqueryvolumeinformationfile">ZwQueryVolumeInformationFile</a> must be at least <b>sizeof</b> (FILE_FS_SECTOR_SIZE_INFORMATION). 

The file system uses the value of <b>LogicalBytesPerSector</b> to determine the size of an allocation unit. The <b>LogicalBytesPerSector</b> member of this structure is equivalent to the <b>BytesPerSector</b> member of the <a href="ifsk.file_fs_size_information">FILE_FS_SIZE_INFORMATION</a>  and <a href="ifsk.file_fs_full_size_information">FILE_FS_FULL_SIZE_INFORMATION</a> structures.

If the system is unable to determine values for <b>PhysicalBytesPerSectorForAtomicity</b> and <b>PhysicalBytesPerSectorForPerformance</b> from the storage device, then they are set to the value of <b>LogicalBytesPerSector.</b>


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
This structure is available starting with Windows 8. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h, Ntifs.h, or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a>
</dt>
<dt>
<a href="ifsk.fsrtlgetsectorsizeinformation">FsRtlGetSectorSizeInformation</a>
</dt>
<dt>
<a href="kernel.zwqueryvolumeinformationfile">ZwQueryVolumeInformationFile</a>
</dt>
<dt>
<a href="ifsk.file_fs_size_information">FILE_FS_SIZE_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.file_fs_full_size_information">FILE_FS_FULL_SIZE_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.irp_mj_query_volume_information">IRP_MJ_QUERY_VOLUME_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_FS_SECTOR_SIZE_INFORMATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

