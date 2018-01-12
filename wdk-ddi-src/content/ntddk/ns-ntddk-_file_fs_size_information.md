---
UID: NS:ntddk._FILE_FS_SIZE_INFORMATION
title: _FILE_FS_SIZE_INFORMATION
author: windows-driver-content
description: The FILE_FS_SIZE_INFORMATION structure is used to query sector size information for a file system volume.
old-location: ifsk\file_fs_size_information.htm
old-project: ifsk
ms.assetid: b7b35df9-04bb-40f0-a076-f4ed5f54ca6c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _FILE_FS_SIZE_INFORMATION, FILE_FS_SIZE_INFORMATION, *PFILE_FS_SIZE_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_FS_SIZE_INFORMATION
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
req.typenames: FILE_FS_SIZE_INFORMATION, *PFILE_FS_SIZE_INFORMATION
---

# _FILE_FS_SIZE_INFORMATION structure



## -description
The FILE_FS_SIZE_INFORMATION structure is used to query sector size information for a file system volume. 



## -syntax

````
typedef struct _FILE_FS_SIZE_INFORMATION {
  LARGE_INTEGER TotalAllocationUnits;
  LARGE_INTEGER AvailableAllocationUnits;
  ULONG         SectorsPerAllocationUnit;
  ULONG         BytesPerSector;
} FILE_FS_SIZE_INFORMATION, *PFILE_FS_SIZE_INFORMATION;
````


## -struct-fields

### -field TotalAllocationUnits

Total number of allocation units on the volume that are available to the user associated with the calling thread. 

<b>Microsoft Windows 2000 and later:</b> If per-user quotas are in use, this value may be less than the total number of allocation units on the disk. 


### -field AvailableAllocationUnits

Total number of free allocation units on the volume that are available to the user associated with the calling thread. 

<b>Windows 2000 and later:</b> If per-user quotas are in use, this value may be less than the total number of free allocation units on the disk. 


### -field SectorsPerAllocationUnit

Number of sectors in each allocation unit. 


### -field BytesPerSector

Number of bytes in each sector. 


## -remarks
This information can be queried in either of the following ways: 

Call <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> or <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>, passing FileFsSizeInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FS_SIZE_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

Create an IRP with major function code IRP_MJ_QUERY_VOLUME_INFORMATION. 

No specific access rights are required to query this information. Thus this information is available as long as the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> or <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a> must be at least <b>sizeof</b> (FILE_FS_SIZE_INFORMATION). 

This structure must be aligned on a LONGLONG (8-byte) boundary. 


## -requirements
<table>
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
<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_FS_SIZE_INFORMATION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

