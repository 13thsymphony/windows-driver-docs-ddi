---
UID: NF:ntifs.FsRtlIncrementCcFastMdlReadWait
title: FsRtlIncrementCcFastMdlReadWait function
author: windows-driver-content
description: The FsRtlIncrementCcFastMdlReadWait routine increments the cache manager's CcFastMdlReadWait performance counter member in a processor control block (PRCB) object.
old-location: ifsk\fsrtlincrementccfastmdlreadwait.htm
old-project: ifsk
ms.assetid: a3a811dc-1dbf-4656-b7ec-bad818f6d1f1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlIncrementCcFastMdlReadWait, FsRtlIncrementCcFastMdlReadWait routine [Installable File System Drivers], fsrtlref_6ab13976-a131-41bf-970c-f2a554d87d92.xml, ifsk.fsrtlincrementccfastmdlreadwait, ntifs/FsRtlIncrementCcFastMdlReadWait
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
-	FsRtlIncrementCcFastMdlReadWait
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlIncrementCcFastMdlReadWait function
The <b>FsRtlIncrementCcFastMdlReadWait </b>routine increments the cache manager's <b>CcFastMdlReadWait</b> performance counter member in a processor control block (<a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PRCB</a>) object.

## Syntax

````
VOID FsRtlIncrementCcFastMdlReadWait(
   VOID 
);
````

## Parameters

This function has no parameters.

## Return Value

This routine does not return a value.

## Remarks

<b>FsRtlIncrementCcFastMdlReadWait </b>increments the cache manager's <b>CcFastMdlReadWait</b> performance counter in the per-processor control block for the processor on which <b>FsRtlIncrementCcFastMdlReadWait</b> is called. This counter records the number of fast I/O <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> read operations (FsRtlMdlRead) serviced by a file system driver.  

File system drivers should call this function to update the <b>CcFastMdlReadWait</b> performance counter if the driver chooses to override the default fast I/O MDL read handler.

The counter is only used to record fast I/O MDL read operations for a nonzero length.  <b>FsRtlIncrementCcFastMdlReadWait</b> should not be called for a zero-length fast I/O MDL read.

File system drivers should not increment the <b>CcFastMdlReadWait</b> performance counter if their fast I/O MDL read handler returns <b>FALSE</b> due to <a href="..\wdm\nf-wdm-iogettoplevelirp.md">IoGetTopLevelIrp</a> returning a non-<b>NULL</b> value.  The counter should only be incremented if the file system driver actually attempts to satisfy a nonzero-length fast I/O MDL read.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating system.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include FltKernel.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-iogettoplevelirp.md">IoGetTopLevelIrp</a>



<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIncrementCcFastMdlReadWait routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>