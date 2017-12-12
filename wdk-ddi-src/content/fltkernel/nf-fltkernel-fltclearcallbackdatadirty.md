---
UID: NF.fltkernel.FltClearCallbackDataDirty
title: FltClearCallbackDataDirty function
author: windows-driver-content
description: The FltClearCallbackDataDirty routine clears the callback dirty flag in a callback data structure.
old-location: ifsk\fltclearcallbackdatadirty.htm
old-project: ifsk
ms.assetid: c53ec6e5-83f8-4262-b832-1a206e6652e6
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltClearCallbackDataDirty
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
req.alt-api: FltClearCallbackDataDirty
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
req.irql: 
---

# FltClearCallbackDataDirty function



## -description
The <b>FltClearCallbackDataDirty</b> routine clears the callback dirty flag in a callback data structure. 



## -syntax

````
VOID FltClearCallbackDataDirty(
  _Inout_ PFLT_CALLBACK_DATA Data
);
````


## -parameters

### -param Data [in, out]

A pointer to a callback data (<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>) structure. 


## -returns
None 


## -remarks
To set an <a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a> structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="ifsk.fltsetcallbackdatadirty">FltSetCallbackDataDirty</a>. 

To test a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="ifsk.fltiscallbackdatadirty">FltIsCallbackDataDirty</a>. 


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
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="ifsk.fltiscallbackdatadirty">FltIsCallbackDataDirty</a>
</dt>
<dt>
<a href="ifsk.fltsetcallbackdatadirty">FltSetCallbackDataDirty</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltClearCallbackDataDirty routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

