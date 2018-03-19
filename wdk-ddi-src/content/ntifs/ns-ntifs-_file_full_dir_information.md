---
UID: NS:ntifs._FILE_FULL_DIR_INFORMATION
title: "_FILE_FULL_DIR_INFORMATION"
author: windows-driver-content
description: The FILE_FULL_DIR_INFORMATION structure is used to query detailed information for the files in a directory.
old-location: ifsk\file_full_dir_information.htm
old-project: ifsk
ms.assetid: 31b1c2f6-415b-4183-8016-51686c460889
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_FULL_DIR_INFORMATION, FILE_FULL_DIR_INFORMATION, FILE_FULL_DIR_INFORMATION structure [Installable File System Drivers], PFILE_FULL_DIR_INFORMATION, PFILE_FULL_DIR_INFORMATION structure pointer [Installable File System Drivers], _FILE_FULL_DIR_INFORMATION, fileinformationstructures_2dfa5780-08bf-4cb8-96f6-c247baaa813a.xml, ifsk.file_full_dir_information, ntifs/FILE_FULL_DIR_INFORMATION, ntifs/PFILE_FULL_DIR_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FILE_FULL_DIR_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_FULL_DIR_INFORMATION, *PFILE_FULL_DIR_INFORMATION
---

# _FILE_FULL_DIR_INFORMATION structure
The FILE_FULL_DIR_INFORMATION structure is used to query detailed information for the files in a directory.

## Syntax
````
typedef struct _FILE_FULL_DIR_INFORMATION {
  ULONG         NextEntryOffset;
  ULONG         FileIndex;
  LARGE_INTEGER CreationTime;
  LARGE_INTEGER LastAccessTime;
  LARGE_INTEGER LastWriteTime;
  LARGE_INTEGER ChangeTime;
  LARGE_INTEGER EndOfFile;
  LARGE_INTEGER AllocationSize;
  ULONG         FileAttributes;
  ULONG         FileNameLength;
  ULONG         EaSize;
  WCHAR         FileName[1];
} FILE_FULL_DIR_INFORMATION, *PFILE_FULL_DIR_INFORMATION;
````

## Members


`NextEntryOffset`

Byte offset of the next FILE_FULL_DIR_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one.

`FileIndex`

Byte offset of the file within the parent directory. This member is undefined for file systems, such as NTFS, in which the position of a file within the parent directory is not fixed and can be changed at any time to maintain sort order.

`CreationTime`

Time when the file was created.

`LastAccessTime`

Last time the file was accessed.

`LastWriteTime`

Last time information was written to the file.

`ChangeTime`

Last time the file was changed.

`EndOfFile`

Absolute new end-of-file position as a byte offset from the start of the file. <b>EndOfFile</b> specifies the byte offset to the end of the file. Because this value is zero-based, it actually refers to the first free byte in the file. In other words, <b>EndOfFile</b> is the offset to the byte immediately following the last valid byte in the file.

`AllocationSize`

File allocation size, in bytes. Usually, this value is a multiple of the sector or cluster size of the underlying physical device.

`FileAttributes`

File attributes, which can be any valid combination of the following: 
	  


<dl>
<dd>FILE_ATTRIBUTE_READONLY</dd>
<dd>FILE_ATTRIBUTE_HIDDEN</dd>
<dd>FILE_ATTRIBUTE_SYSTEM</dd>
<dd>FILE_ATTRIBUTE_DIRECTORY</dd>
<dd>FILE_ATTRIBUTE_ARCHIVE</dd>
<dd>FILE_ATTRIBUTE_NORMAL</dd>
<dd>FILE_ATTRIBUTE_TEMPORARY</dd>
<dd>FILE_ATTRIBUTE_COMPRESSED</dd>
</dl>

`FileNameLength`

Specifies the length of the file name string.

`EaSize`

Combined length, in bytes, of the extended attributes (EA) for the file.

`FileName`

Specifies the first character of the file name string. This is followed in memory by the remainder of the string.

## Remarks
This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="..\ntifs\nf-ntifs-zwquerydirectoryfile.md">ZwQueryDirectoryFile</a>, passing FileFullDirectoryInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FULL_DIR_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_DIRECTORY_CONTROL and minor function code IRP_MN_QUERY_DIRECTORY. 

</li>
</ul>
No specific access rights are required to query this information. 

All dates and times are in absolute system-time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601. 

This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>



<a href="..\ntifs\nf-ntifs-zwquerydirectoryfile.md">ZwQueryDirectoryFile</a>



<a href="..\rxprocs\nf-rxprocs-fsrtlnotifyfullchangedirectory.md">FsRtlNotifyFullChangeDirectory</a>