---
UID: NF.fltkernel.FltSetInstanceContext
title: FltSetInstanceContext function
author: windows-driver-content
description: FltSetInstanceContext sets a context for a minifilter driver instance.
old-location: ifsk\fltsetinstancecontext.htm
old-project: ifsk
ms.assetid: ddeeb49b-7c7d-4faa-b2ae-cdb09adebce0
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltSetInstanceContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available and supported in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later versions of the operating system. Not available nor supported on Windows 2000 SP4 and earlier operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltSetInstanceContext
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

# FltSetInstanceContext function



## -description
<b>FltSetInstanceContext</b> sets a context for a minifilter driver instance. 



## -syntax

````
NTSTATUS FltSetInstanceContext(
  _In_  PFLT_INSTANCE             Instance,
  _In_  FLT_SET_CONTEXT_OPERATION Operation,
  _In_  PFLT_CONTEXT              NewContext,
  _Out_ PFLT_CONTEXT              *OldContext
);
````


## -parameters

### -param Instance [in]

Opaque instance pointer for the instance. 


### -param Operation [in]

Flag specifying details of the operation to be performed. This parameter must be one of the following: 




### -param FLT_SET_CONTEXT_REPLACE_IF_EXISTS

If a context is already set for this <i>Instance</i>, replace it with <i>NewContext</i>. Otherwise, set <i>NewContext</i> as the context for <i>Instance</i>. 


### -param FLT_SET_CONTEXT_KEEP_IF_EXISTS

If a context is already set for this <i>Instance</i>, return STATUS_FLT_CONTEXT_ALREADY_DEFINED. Otherwise, set <i>NewContext</i> as the context for <i>Instance</i>. 

</dd>
</dl>

### -param NewContext [in]

Pointer to the new context to be set for the instance. This parameter is required and cannot be <b>NULL</b>. 


### -param OldContext [out]

Pointer to a caller-allocated variable that receives the address of the existing instance context, if one is already set. This parameter is optional and can be <b>NULL</b>. (For more information about this parameter, see the following Remarks section.) 


## -returns

<a href="kernel.zwsetinformationfile">FltSetInstanceContext</a> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_DEFINED</b></dt>
</dl>If FLT_SET_CONTEXT_KEEP_IF_EXISTS was specified for <i>Operation</i>, this error code indicates that a context is already attached to the instance. Only one context can be attached to an instance. 
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_LINKED</b></dt>
</dl>The context pointed to by the <i>NewContext</i> parameter is already linked to an object.  In other words, this error code indicates that <i>NewContext</i> is already in use due to a successful prior call of an <b>FltSet</b><i>Xxx</i><b>Context</b> routine.
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The specified <i>Instance</i> is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>One of the following: 

The <i>NewContext</i> parameter does not point to a valid instance context. 

An invalid value was specified for <i>Operation</i>. 

 


## -remarks
A minifilter driver calls <a href="kernel.zwsetinformationfile">FltSetInstanceContext</a> to attach an instance context to a caller-owned minifilter driver instance or to remove or replace an existing instance context. A minifilter driver can attach only one context to an instance. 

A successful call to <a href="kernel.zwsetinformationfile">FltSetInstanceContext</a> increments the reference count on <i>NewContext</i>. If <b>FltSetInstanceContext</b> fails, the reference count remains unchanged. In either case, the filter calling <b>FltSetInstanceContext</b> must call <a href="ifsk.fltreleasecontext">FltReleaseContext</a> to decrement the <i>NewContext</i> object. If <b>FltSetInstanceContext</b> fails and if the <i>OldContext</i> parameter is not <b>NULL</b> and does not point to NULL_CONTEXT then <i>OldContext</i> is a referenced pointer to the context currently associated with the transaction. The filter calling <b>FltSetInstanceContext</b> must call <b>FltReleaseContext</b> for <i>OldContext</i> as well.

Note that the <i>OldContext</i> pointer returned by <a href="kernel.zwsetinformationfile">FltSetInstanceContext</a> must also be released by calling <a href="ifsk.fltreleasecontext">FltReleaseContext</a> when it is no longer needed. For more information, see <a href="ifsk.setting_contexts">Setting Contexts</a> and <a href="ifsk.releasing_contexts">Releasing Contexts</a>. 

To get an instance context, call <a href="ifsk.fltgetinstancecontext">FltGetInstanceContext</a>. 

To allocate a new context, call <a href="ifsk.fltallocatecontext">FltAllocateContext</a>. 

To delete an instance context, call <a href="ifsk.fltdeleteinstancecontext">FltDeleteInstanceContext</a> or <a href="ifsk.fltdeletecontext">FltDeleteContext</a>. 

For more information about context reference counting, see <a href="ifsk.referencing_contexts">Referencing Contexts</a>.


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
Version

</th>
<td width="70%">
Available and supported in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later versions of the operating system. Not available nor supported on Windows 2000 SP4 and earlier operating systems.

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
<a href="ifsk.fltdeletecontext">FltDeleteContext</a>
</dt>
<dt>
<a href="ifsk.fltdeleteinstancecontext">FltDeleteInstanceContext</a>
</dt>
<dt>
<a href="ifsk.fltgetinstancecontext">FltGetInstanceContext</a>
</dt>
<dt>
<a href="ifsk.fltreleasecontext">FltReleaseContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetInstanceContext function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

