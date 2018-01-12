---
UID: NF:fltkernel.FltGetStreamContext
title: FltGetStreamContext function
author: windows-driver-content
description: The FltGetStreamContext routine retrieves a context that was set for a file stream by a given minifilter driver instance.
old-location: ifsk\fltgetstreamcontext.htm
old-project: ifsk
ms.assetid: c076390d-42b0-4c8f-b9b1-9db910068795
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltGetStreamContext
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
req.alt-api: FltGetStreamContext
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
req.typenames: EXpsFontRestriction
---

# FltGetStreamContext function



## -description
The <b>FltGetStreamContext</b> routine retrieves a context that was set for a file stream by a given minifilter driver instance. 



## -syntax

````
NTSTATUS FltGetStreamContext(
  _In_  PFLT_INSTANCE Instance,
  _In_  PFILE_OBJECT  FileObject,
  _Out_ PFLT_CONTEXT  *Context
);
````


## -parameters

### -param Instance [in]

Opaque instance pointer for the minifilter driver instance whose context is to be retrieved. 


### -param FileObject [in]

Pointer to a file object for the stream. 


### -param Context [out]

Pointer to a caller-allocated variable that receives the address of the context. 


## -returns
<b>FltGetStreamContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>No matching context was found. This is an error code. 
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The file system does not support per-stream contexts for this file stream. This is an error code. 

 


## -remarks
<b>FltGetStreamContext</b> retrieves a context that was set for a file stream by a given minifilter driver instance. 

<b>FltGetStreamContext</b> increments the reference count on the context that the <i>Context </i>parameter points to. When this context pointer is no longer needed, the caller must decrement its reference count by calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>. Thus every successful call to <b>FltGetStreamContext</b> must be matched by a subsequent call to <b>FltReleaseContext</b>. 

To set a context for a file stream, call <a href="..\fltkernel\nf-fltkernel-fltsetstreamcontext.md">FltSetStreamContext</a>. 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To delete a stream context, call <a href="..\fltkernel\nf-fltkernel-fltdeletestreamcontext.md">FltDeleteStreamContext</a> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeletestreamcontext.md">FltDeleteStreamContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetstreamcontext.md">FltSetStreamContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetStreamContext routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

