---
UID: NF.fltkernel.FltDeleteStreamContext
title: FltDeleteStreamContext function
author: windows-driver-content
description: FltDeleteStreamContext removes a context that a given minifilter driver instance has set for a given stream and marks the context for deletion.
old-location: ifsk\fltdeletestreamcontext.htm
old-project: ifsk
ms.assetid: 49f7d633-3e8b-4c9c-b14a-7ae8f997ad2f
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltDeleteStreamContext
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
req.alt-api: FltDeleteStreamContext
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
---

# FltDeleteStreamContext function



## -description
<b>FltDeleteStreamContext</b> removes a context that a given minifilter driver instance has set for a given stream and marks the context for deletion. 


## -syntax

````
NTSTATUS FltDeleteStreamContext(
  _In_  PFLT_INSTANCE Instance,
  _In_  PFILE_OBJECT  FileObject,
  _Out_ PFLT_CONTEXT  *OldContext
);
````


## -parameters

### -param Instance [in]

Opaque instance pointer for the minifilter driver instance whose context is to be removed from the list of contexts attached to the file stream. 

### -param FileObject [in]

Pointer to a file object for the file stream. 

### -param OldContext [out]

Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be <b>NULL</b>. If <i>OldContext</i> is not <b>NULL</b> and does not point to NULL_CONTEXT, the caller is responsible for calling <a href="ifsk.fltreleasecontext">FltReleaseContext</a> to release this context when it is no longer needed. 

## -returns
<b>FltDeleteStreamContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The specified <i>Instance</i> is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>No matching context was found. This is an error code. 
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The file system does not support per-stream contexts for this file stream. This is an error code. 

 

## -remarks
Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteStreamContext</b> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteStreamContext</b> to remove a context from a file stream and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still in use by another thread). 

To allocate a new context, call <a href="ifsk.fltallocatecontext">FltAllocateContext</a>. 

To get a stream context, call <a href="ifsk.fltgetstreamcontext">FltGetStreamContext</a>. 

To set a stream context, call <a href="ifsk.fltsetstreamcontext">FltSetStreamContext</a>. 

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
<a href="ifsk.fltallocatecontext">FltAllocateContext</a>
</dt>
<dt>
<a href="ifsk.fltdeletecontext">FltDeleteContext</a>
</dt>
<dt>
<a href="ifsk.fltgetstreamcontext">FltGetStreamContext</a>
</dt>
<dt>
<a href="ifsk.fltreleasecontext">FltReleaseContext</a>
</dt>
<dt>
<a href="ifsk.fltsetstreamcontext">FltSetStreamContext</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDeleteStreamContext function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
