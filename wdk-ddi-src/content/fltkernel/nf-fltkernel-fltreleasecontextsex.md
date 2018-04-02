---
UID: NF:fltkernel.FltReleaseContextsEx
title: FltReleaseContextsEx function
author: windows-driver-content
description: FltReleaseContextsEx releases each context in a given FLT_RELATED_CONTEXTS_EX structure.
old-location: ifsk\fltreleasecontextsex.htm
old-project: ifsk
ms.assetid: AC0811C9-8746-40F4-801E-6A1567ABDE0B
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltReleaseContextsEx, FltReleaseContextsEx routine [Installable File System Drivers], fltkernel/FltReleaseContextsEx, ifsk.fltreleasecontextsex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltReleaseContextsEx
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltReleaseContextsEx function
<b>FltReleaseContextsEx</b> releases each context in a given <a href="https://msdn.microsoft.com/library/windows/hardware/hh967703">FLT_RELATED_CONTEXTS_EX</a> structure.

## Syntax

```
VOID FLTAPI FltReleaseContextsEx(
  SIZE_T                   ContextsSize,
  PFLT_RELATED_CONTEXTS_EX Contexts
);
```

## Parameters

`ContextsSize`

The size, in bytes, of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh967703">FLT_RELATED_CONTEXTS_EX</a> structure pointed to by <i>Contexts</i>. Set to <b>sizeof</b>(FLT_RELATED_CONTEXTS_EX).

`Contexts`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh967703">FLT_RELATED_CONTEXTS_EX</a> structure.


## Return Value

None

## Remarks

<b>FltReleaseContextsEx</b> decrements the reference count on all contexts in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh967703">FLT_RELATED_CONTEXTS_EX</a> structure and sets all members of the structure to NULL_CONTEXT. 

To get the <a href="https://msdn.microsoft.com/library/windows/hardware/hh967703">FLT_RELATED_CONTEXTS_EX</a> structure for a given minifilter driver for a given I/O request, call <a href="https://msdn.microsoft.com/library/windows/hardware/hh967699">FltGetContextsEx</a>. 

For more information about context reference counting, see <a href="https://msdn.microsoft.com/9ac3aedb-e057-4e19-9de5-709311072b09">Referencing Contexts</a>. 

Callers of <b>FltReleaseContextsEx</b> must be running at IRQL &lt;= DISPATCH_LEVEL if all contexts were allocated from nonpaged pool. If any contexts were allocated from paged pool, callers must be running at IRQL &lt;= APC_LEVEL. 

When each context's reference count reaches zero, the context is freed immediately if the caller is running at IRQL &lt;= APC_LEVEL. If the caller is running at IRQL DISPATCH_LEVEL, a work item is scheduled to free the context.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | See Remarks section. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544629">FLT_CONTEXT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967703">FLT_RELATED_CONTEXTS_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967699">FltGetContextsEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>