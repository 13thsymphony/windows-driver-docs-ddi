---
UID: NS:fltkernel._FLT_RELATED_CONTEXTS_EX
title: "_FLT_RELATED_CONTEXTS_EX"
author: windows-driver-content
description: The FLT_RELATED_CONTEXTS_EX structure contains a minifilter driver's contexts for the objects associated with an I/O operation.
old-location: ifsk\flt_related_contexts_ex.htm
old-project: ifsk
ms.assetid: 9D3E77AE-C63D-4253-8520-6A9ACCBB89CC
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFLT_RELATED_CONTEXTS_EX, FLT_RELATED_CONTEXTS_EX, FLT_RELATED_CONTEXTS_EX structure [Installable File System Drivers], PFLT_RELATED_CONTEXTS_EX, PFLT_RELATED_CONTEXTS_EX structure pointer [Installable File System Drivers], _FLT_RELATED_CONTEXTS_EX, fltkernel/FLT_RELATED_CONTEXTS_EX, fltkernel/PFLT_RELATED_CONTEXTS_EX, ifsk.flt_related_contexts_ex"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltkernel.h
api_name:
-	FLT_RELATED_CONTEXTS_EX
product: Windows
targetos: Windows
req.typenames: FLT_RELATED_CONTEXTS_EX, *PFLT_RELATED_CONTEXTS_EX
---

# _FLT_RELATED_CONTEXTS_EX structure
The <b>FLT_RELATED_CONTEXTS_EX</b> structure contains a minifilter driver's contexts for the objects associated with an I/O operation.  This structure extends the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544812">FLT_RELATED_CONTEXTS</a> structure to include the section context.

## Syntax
```
typedef struct _FLT_RELATED_CONTEXTS_EX {
  PFLT_CONTEXT VolumeContext;
  PFLT_CONTEXT InstanceContext;
  PFLT_CONTEXT FileContext;
  PFLT_CONTEXT StreamContext;
  PFLT_CONTEXT StreamHandleContext;
  PFLT_CONTEXT TransactionContext;
  PFLT_CONTEXT SectionContext;
} FLT_RELATED_CONTEXTS_EX, *PFLT_RELATED_CONTEXTS_EX;
```

## Members


`VolumeContext`

Opaque pointer to the minifilter's context for the volume that the <b>Volume</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to.

`InstanceContext`

Opaque pointer to the minifilter driver's context for the instance that the <b>Instance</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to.

`FileContext`

An opaque pointer to the minifilter driver's per-file context for the stream handle that the <b>FileObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to.

`StreamContext`

Opaque pointer to the minifilter's stream context for the stream handle that the <b>FileObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to.

`StreamHandleContext`

Opaque pointer to the minifilter's stream handle context for the stream handle that the <b>FileObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to.

`TransactionContext`

An opaque pointer to the minifilter's transaction context for the transaction that the <b>Transaction</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to.

`SectionContext`

An opaque pointer to the minifilter's section context for the stream handle that the <b>FileObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to.

## Remarks
The <b>FLT_RELATED_CONTEXTS_EX</b> structure contains a minifilter driver's contexts for the objects associated with an I/O operation or an instance setup or teardown operation. 

A minifilter driver uses the <b>FLT_RELATED_CONTEXTS_EX</b> structure to retrieve multiple contexts for a given operation. To do so, the minifilter driver allocates an empty <b>FLT_RELATED_CONTEXTS_EX</b> structure and passes a pointer to it as the <i>Contexts</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/hh967699">FltGetContextsEx</a>. 

A minifilter can also use this structure to release multiple contexts for a given operation. To do so, the minifilter driver passes a pointer to <b>FLT_RELATED_CONTEXTS_EX</b> as the <i>Contexts</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/hh967701">FltReleaseContextsEx</a>. 

For more information about using contexts, see the reference entry for <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | fltkernel.h (include Fltkernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544629">FLT_CONTEXT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967699">FltGetContextsEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967701">FltReleaseContextsEx</a>