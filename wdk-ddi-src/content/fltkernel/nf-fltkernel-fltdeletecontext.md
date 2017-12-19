---
UID: NF.fltkernel.FltDeleteContext
title: FltDeleteContext function
author: windows-driver-content
description: FltDeleteContext marks a specified context for deletion.
old-location: ifsk\fltdeletecontext.htm
old-project: ifsk
ms.assetid: 1cdb0747-7616-414b-8287-1ef73637ed05
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltDeleteContext
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
req.alt-api: FltDeleteContext
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
---

# FltDeleteContext function



## -description
<b>FltDeleteContext</b> marks a specified context for deletion. 



## -syntax

````
VOID FltDeleteContext(
  _In_ PFLT_CONTEXT Context
);
````


## -parameters

### -param Context [in]

A pointer to the context to delete. This parameter is required and cannot be <b>NULL</b>. 


## -returns
None. 


## -remarks
Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine, such as <b>FltDeleteContext</b>, to explicitly delete a context. 

<b>FltDeleteContext</b> marks a context for deletion. The context is usually freed as soon as the current reference on it is released, unless there is an outstanding reference on it (for example, because the context is still being used by another thread). 

You should consider the following items when you use <b>FltDeleteContext</b>:

When a minifilter driver calls <b>FltDeleteContext</b>, the minifilter driver must already have a reference to the context. However, when the minifilter driver calls <a href="ifsk.fltdeletestreamhandlecontext">FltDeleteStreamHandleContext</a>, <a href="ifsk.fltdeletestreamcontext">FltDeleteStreamContext</a>, <a href="ifsk.fltdeleteinstancecontext">FltDeleteInstanceContext</a>, and so on, the minifilter driver does not require a reference to the context. After the minifilter driver calls <b>FltDeleteContext</b>, that reference to the context is still valid. The minifilter driver must call the <a href="ifsk.fltreleasecontext">FltReleaseContext</a> routine to release the reference to the context. 

<b>FltDeleteContext</b> removes the context from the internal filter manager structures. Then, further calls to functions that retrieve contexts, such as  <a href="ifsk.fltgetcontexts">FltGetContexts</a> and <a href="ifsk.fltgetinstancecontext">FltGetInstanceContext</a>, cannot locate that context. However, the context memory is not released until the reference count for the context goes to 0. 

Contexts can also be deleted by calling the appropriate delete-context routine from the following table. 

FLT_FILE_CONTEXT


<a href="ifsk.fltdeletefilecontext">FltDeleteFileContext</a> (Windows Vista and later only.)

FLT_INSTANCE_CONTEXT


<a href="ifsk.fltdeleteinstancecontext">FltDeleteInstanceContext</a>


FLT_SECTION_CONTEXT


<a href="ifsk.fltclosesectionfordatascan">FltCloseSectionForDataScan</a> (Windows 8 and later only.)

FLT_STREAM_CONTEXT


<a href="ifsk.fltdeletestreamcontext">FltDeleteStreamContext</a>


FLT_STREAMHANDLE_CONTEXT


<a href="ifsk.fltdeletestreamhandlecontext">FltDeleteStreamHandleContext</a>


FLT_TRANSACTION_CONTEXT


<a href="ifsk.fltdeletetransactioncontext">FltDeleteTransactionContext</a> (Windows Vista and later only.)

FLT_VOLUME_CONTEXT


<a href="ifsk.fltdeletevolumecontext">FltDeleteVolumeContext</a>


To allocate a new context, call <a href="ifsk.fltallocatecontext">FltAllocateContext</a>. 

To increment the reference count on a context, call <a href="ifsk.fltreferencecontext">FltReferenceContext</a>. 

To decrement the reference count on a context, call <a href="ifsk.fltreleasecontext">FltReleaseContext</a>. 

A section context, FLT_SECTION_CONTEXT type, must not be deleted using <b>FltDeleteContext</b>. Instead, use  <a href="ifsk.fltreleasecontext">FltReleaseContext</a> to deallocate a section context.


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
<a href="ifsk.fltallocatecontext">FltAllocateContext</a>
</dt>
<dt>
<a href="ifsk.fltclosesectionfordatascan">FltCloseSectionForDataScan</a>
</dt>
<dt>
<a href="ifsk.fltdeletefilecontext">FltDeleteFileContext</a>
</dt>
<dt>
<a href="ifsk.fltdeleteinstancecontext">FltDeleteInstanceContext</a>
</dt>
<dt>
<a href="ifsk.fltdeletestreamcontext">FltDeleteStreamContext</a>
</dt>
<dt>
<a href="ifsk.fltdeletestreamhandlecontext">FltDeleteStreamHandleContext</a>
</dt>
<dt>
<a href="ifsk.fltdeletetransactioncontext">FltDeleteTransactionContext</a>
</dt>
<dt>
<a href="ifsk.fltdeletevolumecontext">FltDeleteVolumeContext</a>
</dt>
<dt>
<a href="ifsk.fltreferencecontext">FltReferenceContext</a>
</dt>
<dt>
<a href="ifsk.fltreleasecontext">FltReleaseContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDeleteContext function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

