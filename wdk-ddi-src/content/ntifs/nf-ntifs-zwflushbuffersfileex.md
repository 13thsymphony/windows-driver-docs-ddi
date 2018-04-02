---
UID: NF:ntifs.ZwFlushBuffersFileEx
title: ZwFlushBuffersFileEx function
author: windows-driver-content
description: The ZwFlushBuffersFileEx routine is called by a file system filter driver to send a flush request for a given file to the file system. An optional flush operation flag can be set to control how file data is written to storage.
old-location: kernel\zwflushbuffersfileex.htm
old-project: kernel
ms.assetid: C081CCF5-D13C-405C-A430-31805A16724A
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: FLUSH_FLAGS_FILE_DATA_ONLY, FLUSH_FLAGS_NO_SYNC, NtFlushBuffersFileEx, ZwFlushBuffersFileEx, ZwFlushBuffersFileEx routine [Kernel-Mode Driver Architecture], kernel.zwflushbuffersfileex, ntifs/NtFlushBuffersFileEx, ntifs/ZwFlushBuffersFileEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: PASSIVE_LEVEL (See Remarks section.)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwFlushBuffersFileEx
-	NtFlushBuffersFileEx
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# ZwFlushBuffersFileEx function
The <b>ZwFlushBuffersFileEx</b> routine is called by a file system filter driver to send a flush request for a given file to the file system. An optional flush operation flag can be set to control how file data is written to storage.

## Syntax

```
NTSYSAPI NTSTATUS ZwFlushBuffersFileEx(
  HANDLE           FileHandle,
  ULONG            FLags,
  PVOID            Parameters,
  ULONG            ParametersSize,
  PIO_STATUS_BLOCK IoStatusBlock
);
```

## Parameters

`FileHandle`

Handle returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567011">ZwOpenFile</a> for the file whose buffers will be flushed. This parameter is required and cannot be <b>NULL</b>.

`FLags`

TBD

`Parameters`

TBD

`ParametersSize`

TBD

`IoStatusBlock`

Address of the caller's I/O status block. This parameter is required and cannot be <b>NULL</b>.


## Return Value

<b>ZwFlushBuffersFileEx</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MEDIA_WRITE_PROTECTED</b></dt>
</dl>
</td>
<td width="60%">
The file resides on a write-protected volume; this is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_VOLUME_DISMOUNTED</b></dt>
</dl>
</td>
<td width="60%">
The file resides on a volume that is not currently mounted; this is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The file does has neither write or append access.

</td>
</tr>
</table>

## Remarks

A file system filter driver can call <b>ZwFlushBuffersFileEx</b> to issue an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a> request to the file system for a given file. The flush operation is synchronous. 

Minifilter drivers should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542099">FltFlushBuffers</a> instead of calling <b>ZwFlushBuffersFileEx</b>. 

Callers of <b>ZwFlushBuffersFileEx</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwFlushBuffersFileEx</b> function occurs in user mode, you should use the name "<b>NtFlushBuffersFileEx</b>" instead of "<b>ZwFlushBuffersFileEx</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL (See Remarks section.) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542099">FltFlushBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567011">ZwOpenFile</a>