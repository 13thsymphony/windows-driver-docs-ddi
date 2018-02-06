---
UID: NF:fltkernel.FltReleaseContexts
title: FltReleaseContexts function
author: windows-driver-content
description: FltReleaseContexts releases each context in a given FLT_RELATED_CONTEXTS structure.
old-location: ifsk\fltreleasecontexts.htm
old-project: ifsk
ms.assetid: 9b6a28ad-f86c-475b-adee-8d2d8b2d6d61
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltReleaseContexts, fltkernel/FltReleaseContexts, ifsk.fltreleasecontexts, FltApiRef_p_to_z_697bebdc-a3c6-4d95-a97d-0de7b819d56f.xml, FltReleaseContexts function [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltReleaseContexts
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltReleaseContexts function
<b>FltReleaseContexts</b> releases each context in a given <a href="..\fltkernel\ns-fltkernel-_flt_related_contexts.md">FLT_RELATED_CONTEXTS</a> structure.

## Syntax

````
VOID FltReleaseContexts(
  _In_ PFLT_RELATED_CONTEXTS Contexts
);
````

## Parameters

`Contexts`

Pointer to the <a href="..\fltkernel\ns-fltkernel-_flt_related_contexts.md">FLT_RELATED_CONTEXTS</a> structure.


## Return Value

None

## Remarks

<b>FltReleaseContexts</b> decrements the reference count on all contexts in the <a href="..\fltkernel\ns-fltkernel-_flt_related_contexts.md">FLT_RELATED_CONTEXTS</a> structure and sets all members of the structure to NULL_CONTEXT. 

To get the <a href="..\fltkernel\ns-fltkernel-_flt_related_contexts.md">FLT_RELATED_CONTEXTS</a> structure for a given minifilter driver for a given I/O request, call <a href="..\fltkernel\nf-fltkernel-fltgetcontexts.md">FltGetContexts</a>. 

For more information about context reference counting, see <a href="https://msdn.microsoft.com/9ac3aedb-e057-4e19-9de5-709311072b09">Referencing Contexts</a>. 

Callers of <b>FltReleaseContexts</b> must be running at IRQL &lt;= DISPATCH_LEVEL if all contexts were allocated from nonpaged pool. If any contexts were allocated from paged pool, callers must be running at IRQL &lt;= APC_LEVEL. 

When each context's reference count reaches zero, the context is freed immediately if the caller is running at IRQL &lt;= APC_LEVEL. If the caller is running at IRQL DISPATCH_LEVEL, a work item is scheduled to free the context.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | See Remarks section. |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>

<a href="..\fltkernel\ns-fltkernel-_flt_related_contexts.md">FLT_RELATED_CONTEXTS</a>

<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>

<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>

<a href="..\fltkernel\nf-fltkernel-fltgetcontexts.md">FltGetContexts</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltReleaseContexts function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>