---
UID: NF.fltkernel.FltUnloadFilter
title: FltUnloadFilter function
author: windows-driver-content
description: A minifilter driver that has loaded a supporting minifilter driver by calling FltLoadFilter can unload the minifilter driver by calling FltUnloadFilter.
old-location: ifsk\fltunloadfilter.htm
old-project: ifsk
ms.assetid: 234907d8-d21e-4303-9508-0673afa471a6
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltUnloadFilter
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
req.alt-api: FltUnloadFilter
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
req.irql: PASSIVE_LEVEL
---

# FltUnloadFilter function



## -description
A minifilter driver that has loaded a supporting minifilter driver by calling <a href="ifsk.fltloadfilter">FltLoadFilter</a> can unload the minifilter driver by calling <b>FltUnloadFilter</b>. 


## -syntax

````
NTSTATUS FltUnloadFilter(
  _In_ PCUNICODE_STRING FilterName
);
````


## -parameters

### -param FilterName [in]

Pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure containing the minifilter driver service name that was passed to <a href="ifsk.fltloadfilter">FltLoadFilter</a>. 

## -returns
<b>FltUnloadFilter</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>A matching minifilter driver was found, but it is already being torn down. This is an error code. 
<dl>
<dt><b>STATUS_FLT_FILTER_NOT_FOUND</b></dt>
</dl>No matching minifilter driver was found. This is an error code. 

 

## -remarks
A minifilter driver that has a dependency on another minifilter driver can unload that minifilter driver by calling <b>FltUnloadFilter</b>. This routine searches for a registered minifilter driver whose service name matches the given <i>FilterName</i> and calls that minifilter driver's <i>FilterUnloadCallback</i> (<a href="..\fltkernel\nc-fltkernel-pflt_filter_unload_callback.md">PFLT_FILTER_UNLOAD_CALLBACK</a>) routine. 

If the supporting minifilter driver did not register a <i>FilterUnloadCallback</i> routine, the call to <b>FltUnloadFilter</b> fails. 

A minifilter driver cannot call <b>FltUnloadFilter</b> to unload itself. 

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
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltloadfilter">FltLoadFilter</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_filter_unload_callback.md">PFLT_FILTER_UNLOAD_CALLBACK</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltUnloadFilter function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
