---
UID: NF:ntifs.FsRtlSetupAdvancedHeader
title: FsRtlSetupAdvancedHeader function
author: windows-driver-content
description: The FsRtlSetupAdvancedHeader macro is used by file systems to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with filter contexts.
old-location: ifsk\fsrtlsetupadvancedheader.htm
old-project: ifsk
ms.assetid: 8bcf7bbf-6c41-4683-9a62-d408b120c7b9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlSetupAdvancedHeader, FsRtlSetupAdvancedHeader function [Installable File System Drivers], fsrtlref_05f86b8b-48c2-4cb4-b09f-8a4dd1b5ed80.xml, ifsk.fsrtlsetupadvancedheader, ntifs/FsRtlSetupAdvancedHeader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlSetupAdvancedHeader
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlSetupAdvancedHeader function
The <b>FsRtlSetupAdvancedHeader</b> macro is used by file systems to initialize an <a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a> structure for use with filter contexts.

## Syntax

````
VOID FsRtlSetupAdvancedHeader(
  _In_ PVOID       AdvancedHeader,
  _In_ PFAST_MUTEX FastMutex
);
````

## Parameters

`AdvHdr`

TBD

`FMutex`

TBD


## Return Value

None

## Remarks

File systems use the <b>FsRtlSetupAdvancedHeader</b> macro to initialize an <a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a> structure for use with filter contexts. 

When the advanced FCB header structure is no longer required, the file system must call <a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a> to free all associated per-stream context structures. 

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Microsoft Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a>



<a href="..\ntifs\nf-ntifs-fsrtlinitperstreamcontext.md">FsRtlInitPerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>



<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_per_stream_context.md">FSRTL_PER_STREAM_CONTEXT</a>