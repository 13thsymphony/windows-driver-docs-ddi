---
UID: NF:dbgeng.IDebugControl3.GetNumberBreakpoints
title: IDebugControl3::GetNumberBreakpoints method
author: windows-driver-content
description: The GetNumberBreakpoints method returns the number of breakpoints for the current process.
old-location: debugger\getnumberbreakpoints.htm
old-project: debugger
ms.assetid: 9faffb72-3559-4db7-a02e-3d93dc751ac3
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetNumberBreakpoints method [Windows Debugging], GetNumberBreakpoints method [Windows Debugging], IDebugControl interface, GetNumberBreakpoints method [Windows Debugging], IDebugControl2 interface, GetNumberBreakpoints method [Windows Debugging], IDebugControl3 interface, GetNumberBreakpoints,IDebugControl3.GetNumberBreakpoints, IDebugControl interface [Windows Debugging], GetNumberBreakpoints method, IDebugControl2 interface [Windows Debugging], GetNumberBreakpoints method, IDebugControl2::GetNumberBreakpoints, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetNumberBreakpoints method, IDebugControl3::GetNumberBreakpoints, IDebugControl::GetNumberBreakpoints, IDebugControl_c5b9bf83-0a0e-4570-8a05-04ca39a4d335.xml, dbgeng/IDebugControl2::GetNumberBreakpoints, dbgeng/IDebugControl3::GetNumberBreakpoints, dbgeng/IDebugControl::GetNumberBreakpoints, debugger.getnumberbreakpoints
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl.GetNumberBreakpoints
-	IDebugControl2.GetNumberBreakpoints
-	IDebugControl3.GetNumberBreakpoints
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugControl3::GetNumberBreakpoints method
The <b>GetNumberBreakpoints</b> method returns the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">breakpoints</a> for the current process.

## Syntax

```
HRESULT GetNumberBreakpoints(
  PULONG Number
);
```

## Parameters

`Number`

Receives the number of breakpoints.


## Return Value

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537856">AddBreakpoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554487">RemoveBreakpoint</a>