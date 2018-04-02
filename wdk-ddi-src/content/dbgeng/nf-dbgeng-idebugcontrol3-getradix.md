---
UID: NF:dbgeng.IDebugControl3.GetRadix
title: IDebugControl3::GetRadix method
author: windows-driver-content
description: The GetRadix method returns the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.
old-location: debugger\getradix.htm
old-project: debugger
ms.assetid: eae478e1-f70c-4344-a6e0-982a668c1f5d
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetRadix method [Windows Debugging], GetRadix method [Windows Debugging], IDebugControl interface, GetRadix method [Windows Debugging], IDebugControl2 interface, GetRadix method [Windows Debugging], IDebugControl3 interface, GetRadix,IDebugControl3.GetRadix, IDebugControl interface [Windows Debugging], GetRadix method, IDebugControl2 interface [Windows Debugging], GetRadix method, IDebugControl2::GetRadix, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetRadix method, IDebugControl3::GetRadix, IDebugControl::GetRadix, IDebugControl_3f4cb732-868a-4944-bcd9-dd1f221824df.xml, dbgeng/IDebugControl2::GetRadix, dbgeng/IDebugControl3::GetRadix, dbgeng/IDebugControl::GetRadix, debugger.getradix
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
-	IDebugControl.GetRadix
-	IDebugControl2.GetRadix
-	IDebugControl3.GetRadix
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugControl3::GetRadix method
The <b>GetRadix</b> method returns the default radix (number base) used by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> when it evaluates and displays MASM expressions, and when it displays symbol information.

## Syntax

```
HRESULT GetRadix(
  PULONG Radix
);
```

## Parameters

`Radix`

Receives the default radix.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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

## Remarks

For more information about the default radix, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556770">SetRadix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552287">n (Set Number Base)</a>