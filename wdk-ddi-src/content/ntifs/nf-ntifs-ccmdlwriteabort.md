---
UID : NF:ntifs.CcMdlWriteAbort
title : CcMdlWriteAbort function
author : windows-driver-content
description : The CcMdlWriteAbort routine frees memory descriptor lists (MDL) created by an earlier call to CcPrepareMdlWrite.
old-location : ifsk\ccmdlwriteabort.htm
old-project : ifsk
ms.assetid : 32b6fc14-dbaa-41d7-a1a7-a805b9a8795a
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ntifs/CcMdlWriteAbort, CcMdlWriteAbort routine [Installable File System Drivers], ifsk.ccmdlwriteabort, CcMdlWriteAbort, ccref_517f25ce-d707-4611-af24-c66010b0d89e.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available on Microsoft Windows XP and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# CcMdlWriteAbort function
The <b>CcMdlWriteAbort</b> routine frees memory descriptor lists (MDL) created by an earlier call to <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>.

## Syntax

````
VOID CcMdlWriteAbort(
  _In_ PFILE_OBJECT FileObject,
  _In_ PMDL         MdlChain
);
````

## Parameters

`FileObject`

File object pointer that was passed to <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>.

`MdlChain`

Address of the MDL chain returned by <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>.


## Return Value

None

## Remarks

File systems call <b>CcMdlWriteAbort</b> to free the memory descriptor lists (MDL) created by an earlier call to <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a> for a cached file. All physical pages that were locked down are unlocked. Any pages that were mapped are unmapped. 

File systems normally call <b>CcMdlWriteAbort</b> only in cases where, after a successful call to <a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>, it is necessary to abort or fail the subsequent MDL write operation. 

Unlike <a href="..\ntifs\nf-ntifs-ccmdlwritecomplete.md">CcMdlWriteComplete</a>, <b>CcMdlWriteAbort</b> does not cause any data to be written to the cached file.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Microsoft Windows XP and later. Available on Microsoft Windows XP and later. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntifs\nf-ntifs-ccmdlwritecomplete.md">CcMdlWriteComplete</a>

<a href="..\ntifs\nf-ntifs-ccpreparemdlwrite.md">CcPrepareMdlWrite</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcMdlWriteAbort routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>