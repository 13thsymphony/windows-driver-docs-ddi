---
UID: NF:fltkernel.FltDeleteFileContext
title: FltDeleteFileContext function
author: windows-driver-content
description: The FltDeleteFileContext routine retrieves and deletes a file context that a given minifilter driver has set for a given file.
old-location: ifsk\fltdeletefilecontext.htm
old-project: ifsk
ms.assetid: faffa053-0382-415c-8f61-ee9121839598
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_a_to_d_53ae4cfc-b70a-405d-b947-cb0f04d4663b.xml, FltDeleteFileContext, FltDeleteFileContext routine [Installable File System Drivers], fltkernel/FltDeleteFileContext, ifsk.fltdeletefilecontext
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
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltDeleteFileContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltDeleteFileContext function
The <b>FltDeleteFileContext</b> routine retrieves and deletes a file context that a given minifilter driver has set for a given file.

## Syntax

```
NTSTATUS FLTAPI FltDeleteFileContext(
  PFLT_INSTANCE Instance,
  PFILE_OBJECT  FileObject,
  PFLT_CONTEXT  *OldContext
);
```

## Parameters

`Instance`

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

`FileObject`

File object pointer for the file. This parameter is required and cannot be <b>NULL</b>.

`OldContext`

Pointer to a caller-allocated variable that receives the address of the deleted context. If no matching context is found, this variable receives NULL_CONTEXT. This parameter is optional and can be <b>NULL</b>. (For more information about this parameter, see the following Remarks section.)


## Return Value

<b>FltDeleteFileContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

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
File contexts are not supported for this file. This is an error code. 

</td>
</tr>
</table>

## Remarks

The <b>FltDeleteFileContext</b> routine is available on Windows Vista and later. 

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteFileContext</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteFileContext</b> to retrieve and delete a file context that it previously set for a file by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544511">FltSetFileContext</a>. 

If the <i>OldContext</i> parameter is <b>NULL</b> on input and a matching file context is found, <b>FltDeleteFileContext</b> releases the reference that was added by the minifilter driver's previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff544511">FltSetFileContext</a>. The deleted context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still being used by another thread). 

If the <i>OldContext</i> parameter is not <b>NULL</b> and a matching file context is found and returned, the caller is responsible for releasing the reference that was added by <a href="https://msdn.microsoft.com/library/windows/hardware/ff544511">FltSetFileContext</a>. To release this reference, the minifilter driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a> on the deleted file context as soon as possible after performing any necessary cleanup. 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To decrement the reference count on a context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>. 

To delete a context for which you already have a context pointer, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>. 

To retrieve a file context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543025">FltGetFileContext</a>. 

To set a file context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544511">FltSetFileContext</a>. 

To determine whether file contexts are supported for a given file, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544574">FltSupportsFileContexts</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff544576">FltSupportsFileContextsEx</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544629">FLT_CONTEXT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543025">FltGetFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544511">FltSetFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544574">FltSupportsFileContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544576">FltSupportsFileContextsEx</a>