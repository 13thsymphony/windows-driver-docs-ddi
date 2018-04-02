---
UID: NS:ntifs._FILE_REPARSE_POINT_INFORMATION
title: "_FILE_REPARSE_POINT_INFORMATION"
author: windows-driver-content
description: The FILE_REPARSE_POINT_INFORMATION structure is used to query for information about a reparse point.
old-location: ifsk\file_reparse_point_information.htm
old-project: ifsk
ms.assetid: de6e8b39-9e0c-4817-82b4-d64e81a95e79
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFILE_REPARSE_POINT_INFORMATION, FILE_REPARSE_POINT_INFORMATION, FILE_REPARSE_POINT_INFORMATION structure [Installable File System Drivers], PFILE_REPARSE_POINT_INFORMATION, PFILE_REPARSE_POINT_INFORMATION structure pointer [Installable File System Drivers], _FILE_REPARSE_POINT_INFORMATION, fileinformationstructures_5e939a71-0fcc-41e9-be0f-c2c1b5327239.xml, ifsk.file_reparse_point_information, ntifs/FILE_REPARSE_POINT_INFORMATION, ntifs/PFILE_REPARSE_POINT_INFORMATION"
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
-	FILE_REPARSE_POINT_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_REPARSE_POINT_INFORMATION, *PFILE_REPARSE_POINT_INFORMATION
---

# _FILE_REPARSE_POINT_INFORMATION structure
The FILE_REPARSE_POINT_INFORMATION structure is used to query for information about a reparse point.

## Syntax
```
typedef struct _FILE_REPARSE_POINT_INFORMATION {
  LONGLONG FileReference;
  ULONG    Tag;
} *PFILE_REPARSE_POINT_INFORMATION, FILE_REPARSE_POINT_INFORMATION;
```

## Members


`FileReference`

The 8-byte file reference number for the file. This number is generated and assigned to the file by the NTFS file system. (Note that the <i>FileId</i> is not the same as the 16-byte "file object ID" that was added to NTFS for Microsoft Windows 2000.)

`Tag`

Reparse point tag. The <b>ReparseTag</b> member indicates the structure of the user-defined reparse data. For more information about reparse point tags, see the Microsoft Windows SDK documentation.

## Remarks
This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff567047">ZwQueryDirectoryFile</a>, passing FileReparsePointInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_REPARSE_POINT_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a> and minor function code IRP_MN_QUERY_DIRECTORY. 

</li>
</ul>
For more information about reparse points, see the Windows SDK documentation. 

No specific access rights are required to query this information. 

This structure must be LONG-aligned.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567047">ZwQueryDirectoryFile</a>