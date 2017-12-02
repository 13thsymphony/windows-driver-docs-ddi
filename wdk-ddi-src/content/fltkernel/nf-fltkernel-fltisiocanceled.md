---
UID: NF.fltkernel.FltIsIoCanceled
title: FltIsIoCanceled
author: windows-driver-content
description: The FltIsIoCanceled routine checks if an IRP-based operation has been canceled.
old-location: ifsk\fltisiocanceled.htm
old-project: ifsk
ms.assetid: a27ec86b-85b3-4d65-a77a-fb6292b935d0
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltIsIoCanceled
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
req.alt-api: FltIsIoCanceled
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
req.irql: Any level
req.iface: 
---

# FltIsIoCanceled function



## -description
<p>The <b>FltIsIoCanceled</b> routine checks if an IRP-based operation has been canceled. </p>


## -syntax

````
BOOLEAN FltIsIoCanceled(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters
<dl>

### -param CallbackData [in]

<dd>
<p>Pointer to the callback data structure for the operation (<a href="..\fltkernel\ns-fltkernel--flt-callback-data.md">FLT_CALLBACK_DATA</a>). </p>
</dd>
</dl>

## -returns
<p><b>FltIsIoCanceled</b> returns <b>TRUE</b> if an IRP-based operation has been canceled and <b>FALSE</b> if the operation has not been canceled or if it is not an IRP-based operation. </p>

## -remarks
<p>It is a programming error to call <b>FltIsIoCanceled</b> for an operation that is not IRP-based. To determine whether the operation is IRP-based, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. </p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
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
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel--flt-callback-data.md">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcancelfileopen.md">FltCancelFileOpen</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcancelio.md">FltCancelIo</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltclearcancelcompletion.md">FltClearCancelCompletion</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetcancelcompletion.md">FltSetCancelCompletion</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltIsIoCanceled routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
