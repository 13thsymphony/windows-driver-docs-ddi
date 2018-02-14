---
UID: NS:ntddk._FILE_FS_VOLUME_INFORMATION
title: "_FILE_FS_VOLUME_INFORMATION"
author: windows-driver-content
description: The FILE_FS_VOLUME_INFORMATION structure is used to query information about a volume on which a file system is mounted.
old-location: ifsk\file_fs_volume_information.htm
old-project: ifsk
ms.assetid: b0c6f733-2d8b-4140-bb2a-2a28212d3e69
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: PFILE_FS_VOLUME_INFORMATION, _FILE_FS_VOLUME_INFORMATION, fileinformationstructures_97bfe785-4c25-4402-91be-0fd2bda36c5d.xml, FILE_FS_VOLUME_INFORMATION, ntddk/FILE_FS_VOLUME_INFORMATION, ntddk/PFILE_FS_VOLUME_INFORMATION, *PFILE_FS_VOLUME_INFORMATION, FILE_FS_VOLUME_INFORMATION structure [Installable File System Drivers], ifsk.file_fs_volume_information, PFILE_FS_VOLUME_INFORMATION structure pointer [Installable File System Drivers]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	FILE_FS_VOLUME_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_FS_VOLUME_INFORMATION, *PFILE_FS_VOLUME_INFORMATION
---

# _FILE_FS_VOLUME_INFORMATION structure
The FILE_FS_VOLUME_INFORMATION structure is used to query information about a volume on which a file system is mounted.

## Syntax
````
typedef struct _FILE_FS_VOLUME_INFORMATION {
  LARGE_INTEGER VolumeCreationTime;
  ULONG         VolumeSerialNumber;
  ULONG         VolumeLabelLength;
  BOOLEAN       SupportsObjects;
  WCHAR         VolumeLabel[1];
} FILE_FS_VOLUME_INFORMATION, *PFILE_FS_VOLUME_INFORMATION;
````

## Members


`SupportsObjects`

<b>TRUE</b> if the file system supports object-oriented file system objects, <b>FALSE</b> otherwise.

`VolumeCreationTime`

Time when the volume was created.

`VolumeLabel`

Name of the volume.

`VolumeLabelLength`

Length, in bytes, of the name of the volume.

`VolumeSerialNumber`

Serial number of the volume.

## Remarks
This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> or <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>, passing FileFsVolumeInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FS_VOLUME_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_QUERY_VOLUME_INFORMATION. 

</li>
</ul>
No specific access rights are required to query this information. Thus this information is available as long as the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume. 

All dates and times are in absolute system-time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> or <a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a> must be at least <b>sizeof</b> (FILE_FS_VOLUME_INFORMATION). 

This structure must be aligned on a LONGLONG (8-byte) boundary.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h, Fltkernel.h) |

## See Also

<a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_FS_VOLUME_INFORMATION structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>