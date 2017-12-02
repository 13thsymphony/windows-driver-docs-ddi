---
UID: NF.dbgeng.IDebugControl2.IsPointer64Bit
title: IDebugControl2::IsPointer64Bit
author: windows-driver-content
description: The IsPointer64Bit method determines if the effective processor uses 64-bit pointers.
old-location: debugger\ispointer64bit.htm
old-project: debugger
ms.assetid: 01003268-844e-4613-ac13-0306396e56b9
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugControl2, IsPointer64Bit, IDebugControl2::IsPointer64Bit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl.IsPointer64Bit,IDebugControl2.IsPointer64Bit,IDebugControl3.IsPointer64Bit
req.alt-loc: dbgeng.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: IDebugControl2
---

# IDebugControl2::IsPointer64Bit method



## -description
<p>The <b>IsPointer64Bit</b> method determines if the effective processor uses 64-bit pointers.</p>


## -syntax

````
HRESULT IsPointer64Bit();
````


## -parameters


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The effective processor uses 64-bit pointers.</p><dl>
<dt><b>S_FALSE</b></dt>
</dl><p>The effective processor does not use 64-bit pointers.</p>

<p> </p>

<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The effective processor uses 64-bit pointers.</p><dl>
<dt><b>S_FALSE</b></dt>
</dl><p>The effective processor does not use 64-bit pointers.</p>

<p> </p>

<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The effective processor uses 64-bit pointers.</p><dl>
<dt><b>S_FALSE</b></dt>
</dl><p>The effective processor does not use 64-bit pointers.</p>

<p> </p>

<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dbgeng.h</dt>
</dl>
</td>
</tr>
</table>