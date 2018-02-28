---
UID: NF:ntifs.FsRtlInitPerStreamContext
title: FsRtlInitPerStreamContext macro
author: windows-driver-content
description: The FsRtlInitPerStreamContext macro initializes a filter driver context structure.
old-location: ifsk\fsrtlinitperstreamcontext.htm
old-project: ifsk
ms.assetid: eea0c2d7-0338-4f34-acae-6ab869011696
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlInitPerStreamContext, FsRtlInitPerStreamContext function [Installable File System Drivers], fsrtlref_13a48f5e-d3e7-49fa-8c4c-bb2d061f2b2a.xml, ifsk.fsrtlinitperstreamcontext, ntifs/FsRtlInitPerStreamContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: The FsRtlInitPerStreamContext macro is available on Microsoft Windows XP and later, and on the Update Rollup for Windows 2000 Service Pack 4 (SP4).
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
req.lib: ntifs.h
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlInitPerStreamContext
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlInitPerStreamContext function
The <b>FsRtlInitPerStreamContext</b> macro initializes a filter driver context structure.

## Syntax

````
VOID FsRtlInitPerStreamContext(
  _In_ PFSRTL_PER_STREAM_CONTEXT PerStreamContext,
  _In_ PVOID                     OwnerId,
  _In_ PVOID                     InstanceId,
  _In_ PFREE_FUNCTION            FreeCallback
);
````

## Parameters

`_fc`

TBD

`_owner`

TBD

`_inst`

TBD

`_cb`

TBD


## Return Value

None

## Remarks

A file system filter driver uses the <b>FsRtlInitPerStreamContext</b> macro to initialize a newly allocated per-stream context structure before associating it with a file stream. The initialized context structure can be passed as a parameter to <a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>. 

<b>FsRtlInitPerStreamContext</b> stores the address of the <i>FreeCallback</i> routine in the <b>FreeCallback</b> member of the FSRTL_PER_STREAM_CONTEXT structure. 

The <i>FreeCallback</i> routine is called at IRQL &lt;= APC_LEVEL. Usually, it is called at IRQL PASSIVE_LEVEL. 

<div class="alert"><b>Note</b>    The <i>FreeCallback</i> routine cannot recursively call down into the file system or acquire any file system resources. Also, this routine must assume that the file object for the file stream has already been freed. </div>
<div> </div>
To associate an initialized per-stream context structure with a file stream, call <a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>. 

After the context structure has been associated with a file stream, it can be retrieved by calling <a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a> or removed by calling <a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>. 

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The FsRtlInitPerStreamContext macro is available on Microsoft Windows XP and later, and on the Update Rollup for Windows 2000 Service Pack 4 (SP4).  |
| **Target Platform** | Desktop |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | ntifs.h |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a>



<a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md">FsRtlSetupAdvancedHeader</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_per_stream_context.md">FSRTL_PER_STREAM_CONTEXT</a>



<a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>



<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>



<a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>



<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInitPerStreamContext function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>