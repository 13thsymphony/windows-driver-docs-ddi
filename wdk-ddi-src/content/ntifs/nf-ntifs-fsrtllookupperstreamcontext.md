---
UID: NF:ntifs.FsRtlLookupPerStreamContext
title: FsRtlLookupPerStreamContext macro
author: windows-driver-content
description: The FsRtlLookupPerStreamContext macro retrieves a per-stream context structure for a file stream.
old-location: ifsk\fsrtllookupperstreamcontext.htm
old-project: ifsk
ms.assetid: 8f8c47c3-1917-4252-b812-711ef52d22d7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlLookupPerStreamContext, FsRtlLookupPerStreamContext function [Installable File System Drivers], fsrtlref_8284a485-5669-4a4f-a2cf-d566b82299fb.xml, ifsk.fsrtllookupperstreamcontext, ntifs/FsRtlLookupPerStreamContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
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
-	FsRtlLookupPerStreamContext
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlLookupPerStreamContext function
The <b>FsRtlLookupPerStreamContext</b> macro retrieves a per-stream context structure for a file stream.

## Syntax

````
PFSRTL_PER_STREAM_CONTEXT FsRtlLookupPerStreamContext(
  _In_     PFSRTL_ADVANCED_FCB_HEADER StreamContext,
  _In_opt_ PVOID                      OwnerId,
  _In_opt_ PVOID                      InstanceId
);
````

## Parameters

`_sc`

TBD

`_oid`

TBD

`_iid`

TBD


## Return Value

None

## Remarks

A file system filter driver calls <b>FsRtlLookupPerStreamContext</b> to retrieve its per-stream context structure for a file stream. The per-stream context structure contains context information that the filter driver maintains for the file stream. 

<div class="alert"><b>Note</b>  <b>FsRtlLookupPerStreamContext</b>  can only be used on file systems that support per-stream contexts.</div>
<div> </div>
To initialize a per-stream context structure, use the <a href="..\ntifs\nf-ntifs-fsrtlinitperstreamcontext.md">FsRtlInitPerStreamContext</a> macro. 

To associate an initialized per-stream context structure with a file stream, call <a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>. 

To remove a per-stream context structure that is associated with a file stream, call <a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>. 

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a>



<a href="..\ntifs\nf-ntifs-fsrtlinitperstreamcontext.md">FsRtlInitPerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>



<a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_per_stream_context.md">FSRTL_PER_STREAM_CONTEXT</a>



<a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md">FsRtlSetupAdvancedHeader</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlLookupPerStreamContext function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>