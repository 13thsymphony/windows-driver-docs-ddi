---
UID: NF:fltkernel.FltDeleteStreamContext
title: FltDeleteStreamContext function
author: windows-driver-content
description: FltDeleteStreamContext removes a context that a given minifilter driver instance has set for a given stream and marks the context for deletion.
old-location: ifsk\fltdeletestreamcontext.htm
old-project: ifsk
ms.assetid: 49f7d633-3e8b-4c9c-b14a-7ae8f997ad2f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fltkernel/FltDeleteStreamContext, ifsk.fltdeletestreamcontext, FltDeleteStreamContext, FltApiRef_a_to_d_8339a254-56eb-4f75-b294-006286f3ff10.xml, FltDeleteStreamContext function [Installable File System Drivers]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltDeleteStreamContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltDeleteStreamContext function
<b>FltDeleteStreamContext</b> removes a context that a given minifilter driver instance has set for a given stream and marks the context for deletion.

## Syntax

````
NTSTATUS FltDeleteStreamContext(
  _In_  PFLT_INSTANCE Instance,
  _In_  PFILE_OBJECT  FileObject,
  _Out_ PFLT_CONTEXT  *OldContext
);
````

## Parameters

`Instance`

Opaque instance pointer for the minifilter driver instance whose context is to be removed from the list of contexts attached to the file stream.

`FileObject`

Pointer to a file object for the file stream.

`OldContext`

Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be <b>NULL</b>. If <i>OldContext</i> is not <b>NULL</b> and does not point to NULL_CONTEXT, the caller is responsible for calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> to release this context when it is no longer needed.


## Return Value

<b>FltDeleteStreamContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Instance</i> is being torn down. This is an error code. 

</td>
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

Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteStreamContext</b> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteStreamContext</b> to remove a context from a file stream and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still in use by another thread). 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To get a stream context, call <a href="..\fltkernel\nf-fltkernel-fltgetstreamcontext.md">FltGetStreamContext</a>. 

To set a stream context, call <a href="..\fltkernel\nf-fltkernel-fltsetstreamcontext.md">FltSetStreamContext</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltgetstreamcontext.md">FltGetStreamContext</a>



<a href="..\fltkernel\nf-fltkernel-fltsetstreamcontext.md">FltSetStreamContext</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



<a href="..\fltkernel\nf-fltkernel-fltsetstreamcontext.md">FltSetStreamContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDeleteStreamContext function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>