---
UID: NF:dbgeng.IDebugBreakpoint2.GetId
title: IDebugBreakpoint2::GetId method
author: windows-driver-content
description: The GetId method returns a breakpoint ID, which is the engine's unique identifier for a breakpoint.
old-location: debugger\getid.htm
old-project: debugger
ms.assetid: 991d8a40-1991-4c06-9557-9abee3ed8073
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2::GetId, GetId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugBreakpoint.GetId,IDebugBreakpoint2.GetId
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugBreakpoint2::GetId method



## -description
The <b>GetId</b> method returns a breakpoint ID, which is the engine's unique identifier for a breakpoint.



## -syntax

````
HRESULT GetId(
  [out] PULONG Id
);
````


## -parameters

### -param Id [out]

The breakpoint ID.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
The breakpoint ID remains fixed as long as the breakpoint exists.  However, after the breakpoint has been removed, you can use its ID for another breakpoint.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the breakpoint ID.

For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>