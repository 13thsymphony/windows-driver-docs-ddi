---
UID: NF:fltkernel.FltGetStreamContext
title: FltGetStreamContext function
author: windows-driver-content
description: The FltGetStreamContext routine retrieves a context that was set for a file stream by a given minifilter driver instance.
old-location: ifsk\fltgetstreamcontext.htm
old-project: ifsk
ms.assetid: c076390d-42b0-4c8f-b9b1-9db910068795
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_e7a12c32-5aec-433e-86e4-46844f56e75a.xml, FltGetStreamContext, FltGetStreamContext routine [Installable File System Drivers], fltkernel/FltGetStreamContext, ifsk.fltgetstreamcontext
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetStreamContext
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltGetStreamContext function
The <b>FltGetStreamContext</b> routine retrieves a context that was set for a file stream by a given minifilter driver instance.

## Syntax

```
NTSTATUS FLTAPI FltGetStreamContext(
  PFLT_INSTANCE Instance,
  PFILE_OBJECT  FileObject,
  PFLT_CONTEXT  *Context
);
```

## Parameters

`Instance`

Opaque instance pointer for the minifilter driver instance whose context is to be retrieved.

`FileObject`

Pointer to a file object for the stream.

`Context`

Pointer to a caller-allocated variable that receives the address of the context.


## Return Value

<b>FltGetStreamContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching context was found. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The file system does not support per-stream contexts for this file stream. This is an error code. 

</td>
</tr>
</table>

## Remarks

<b>FltGetStreamContext</b> retrieves a context that was set for a file stream by a given minifilter driver instance. 

<b>FltGetStreamContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>. Thus every successful call to <b>FltGetStreamContext</b> must be matched by a subsequent call to <b>FltReleaseContext</b>. 

To set a context for a file stream, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544543">FltSetStreamContext</a>. 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To delete a stream context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541997">FltDeleteStreamContext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541997">FltDeleteStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544543">FltSetStreamContext</a>