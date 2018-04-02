---
UID: NF:ntifs.FsRtlIsPagingFile
title: FsRtlIsPagingFile function
author: windows-driver-content
description: The FsRtlIsPagingFile routine determines whether a given file is a paging file.
old-location: ifsk\fsrtlispagingfile.htm
old-project: ifsk
ms.assetid: 85363a0b-0e62-499e-bcdb-4b86c4a0c3a0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlIsPagingFile, FsRtlIsPagingFile routine [Installable File System Drivers], fsrtlref_80254cb1-bb65-4b1b-8fe4-c975b0f00c63.xml, ifsk.fsrtlispagingfile, ntifs/FsRtlIsPagingFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlIsPagingFile
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlIsPagingFile function
The <b>FsRtlIsPagingFile</b> routine determines whether a given file is a paging file.

## Syntax

```
NTKERNELAPI LOGICAL FsRtlIsPagingFile(
  PFILE_OBJECT FileObject
);
```

## Parameters

`FileObject`

Pointer to a file object for the file.


## Return Value

<b>FsRtlIsPagingFile</b> returns <b>TRUE</b> if the file represented by <i>FileObject</i> is a paging file, otherwise <b>FALSE</b>.

## Remarks

File system filter drivers call <b>FsRtlIsPagingFile</b> to determine whether a given file object represents a paging file. 

<div class="alert"><b>Note</b>    If <b>FsRtlIsPagingFile</b> is called in the create completion ("post-create") path, it returns <b>FALSE</b>, even if the file is a paging file. However, it works properly on Windows Vista and later. </div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547152">FsRtlPostPagingFileStackOverflow</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>