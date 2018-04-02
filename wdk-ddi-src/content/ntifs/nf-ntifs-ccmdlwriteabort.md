---
UID: NF:ntifs.CcMdlWriteAbort
title: CcMdlWriteAbort function
author: windows-driver-content
description: The CcMdlWriteAbort routine frees memory descriptor lists (MDL) created by an earlier call to CcPrepareMdlWrite.
old-location: ifsk\ccmdlwriteabort.htm
old-project: ifsk
ms.assetid: 32b6fc14-dbaa-41d7-a1a7-a805b9a8795a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CcMdlWriteAbort, CcMdlWriteAbort routine [Installable File System Drivers], ccref_517f25ce-d707-4611-af24-c66010b0d89e.xml, ifsk.ccmdlwriteabort, ntifs/CcMdlWriteAbort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcMdlWriteAbort
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# CcMdlWriteAbort function
The <b>CcMdlWriteAbort</b> routine frees memory descriptor lists (MDL) created by an earlier call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539181">CcPrepareMdlWrite</a>.

## Syntax

```
NTKERNELAPI VOID CcMdlWriteAbort(
  PFILE_OBJECT FileObject,
  PMDL         MdlChain
);
```

## Parameters

`FileObject`

File object pointer that was passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539181">CcPrepareMdlWrite</a>.

`MdlChain`

Address of the MDL chain returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff539181">CcPrepareMdlWrite</a>.


## Return Value

None

## Remarks

File systems call <b>CcMdlWriteAbort</b> to free the memory descriptor lists (MDL) created by an earlier call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539181">CcPrepareMdlWrite</a> for a cached file. All physical pages that were locked down are unlocked. Any pages that were mapped are unmapped. 

File systems normally call <b>CcMdlWriteAbort</b> only in cases where, after a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539181">CcPrepareMdlWrite</a>, it is necessary to abort or fail the subsequent MDL write operation. 

Unlike <a href="https://msdn.microsoft.com/library/windows/hardware/ff539172">CcMdlWriteComplete</a>, <b>CcMdlWriteAbort</b> does not cause any data to be written to the cached file.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Microsoft Windows XP and later.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539172">CcMdlWriteComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539181">CcPrepareMdlWrite</a>