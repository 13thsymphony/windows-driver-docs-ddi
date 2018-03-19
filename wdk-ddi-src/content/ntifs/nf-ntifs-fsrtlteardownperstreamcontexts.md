---
UID: NF:ntifs.FsRtlTeardownPerStreamContexts
title: FsRtlTeardownPerStreamContexts function
author: windows-driver-content
description: The FsRtlTeardownPerStreamContexts routine frees all per-stream context structures associated with a given FSRTL_ADVANCED_FCB_HEADER structure.
old-location: ifsk\fsrtlteardownperstreamcontexts.htm
old-project: ifsk
ms.assetid: a37a921c-748a-4ac2-99c7-a6cf987a8f54
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlTeardownPerStreamContexts, FsRtlTeardownPerStreamContexts routine [Installable File System Drivers], fsrtlref_15f597e3-b397-497b-9839-a61b6cf27745.xml, ifsk.fsrtlteardownperstreamcontexts, ntifs/FsRtlTeardownPerStreamContexts
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Microsoft Windows XP and later.
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
-	FsRtlTeardownPerStreamContexts
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlTeardownPerStreamContexts function
The <b>FsRtlTeardownPerStreamContexts</b> routine frees all per-stream context structures associated with a given FSRTL_ADVANCED_FCB_HEADER structure.

## Syntax

````
VOID FsRtlTeardownPerStreamContexts(
  _In_ PFSRTL_ADVANCED_FCB_HEADER AdvancedHeader
);
````

## Parameters

`AdvancedHeader`

Pointer to the FSRTL_ADVANCED_FCB_HEADER structure.


## Return Value

None

## Remarks

File systems call <b>FsRtlTeardownPerStreamContexts</b> to free all per-stream context structures associated with a given FSRTL_ADVANCED_FCB_HEADER structure. When a file system tears down the stream context object for a file stream, it must call <b>FsRtlTeardownPerStreamContexts</b>, which in turn calls the <i>FreeCallback</i> routines of all per-stream context structures associated with the file stream. 

To avoid conflicts in synchronization, the <b>FsRtlTeardownPerStreamContexts</b> routine releases the lock for the per file context objects before calling <i>FreeCallback</i>. This avoids blocking access to the to the per file context objects by the filter for own list operations, such as removal with <a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Microsoft Windows XP and later.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a>



<a href="..\ntifs\nf-ntifs-fsrtlinitperstreamcontext.md">FsRtlInitPerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_per_stream_context.md">FSRTL_PER_STREAM_CONTEXT</a>



<a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>



<a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md">FsRtlSetupAdvancedHeader</a>