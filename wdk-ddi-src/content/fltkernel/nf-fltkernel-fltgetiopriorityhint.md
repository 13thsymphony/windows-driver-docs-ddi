---
UID: NF.fltkernel.FltGetIoPriorityHint
title: FltGetIoPriorityHint
author: windows-driver-content
description: The FltGetIoPriorityHint routine is used by a minifilter driver to get IO priority information from Callback Data.
old-location: ifsk\fltgetiopriorityhint.htm
old-project: ifsk
ms.assetid: 51c2068b-3dde-4e63-985c-51b8f7020948
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: FltGetIoPriorityHint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltGetIoPriorityHint
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
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# FltGetIoPriorityHint function



## -description
<p>The <b>FltGetIoPriorityHint</b> routine is used by a minifilter driver to get IO priority information from Callback Data.</p>


## -syntax

````
IO_PRIORITY_HINT FltGetIoPriorityHint(
  _In_ PFLT_CALLBACK_DATA Data
);
````


## -parameters
<dl>

### -param <i>Data</i> [in]

<dd>
<p>A pointer to a <a href="..\fltkernel\ns-fltkernel--flt-callback-data.md">FLT_CALLBACK_DATA</a> structure that represents an I/O operation. This parameter is required and cannot be <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p>The <b>FltGetIoPriorityHint</b> routine returns an IO priority hint retrieved from a <a href="..\fltkernel\ns-fltkernel--flt-callback-data.md">FLT_CALLBACK_DATA</a> structure.  </p>

## -remarks
<p>The <b>FltGetIoPriorityHint</b> routine retrieves an IO Priority hint from the <i>Data</i><a href="..\fltkernel\ns-fltkernel--flt-callback-data.md">FLT_CALLBACK_DATA</a> structure.  This hint will be based on the following fields in the <b>FLT_CALLBACK_DATA</b>:</p>

<p>IRP (optional)  </p>

<p>FileObject  </p>

<p>Thread  </p>

<p>If these <a href="..\fltkernel\ns-fltkernel--flt-callback-data.md">FLT_CALLBACK_DATA</a> fields do not have an IO priority, the routine returns IoPriorityNormal.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include FltKernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel--flt-callback-data.md">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md">FltGetIoPriorityHintFromCallbackData</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromfileobject.md">FltGetIoPriorityHintFromFileObject</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromthread.md">FltGetIoPriorityHintFromThread</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintocallbackdata.md">FltSetIoPriorityHintIntoCallbackData</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md">FltSetIoPriorityHintIntoFileObject</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md">FltSetIoPriorityHintIntoThread</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs--io-priority-info.md">IO_PRIORITY_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetIoPriorityHint routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
