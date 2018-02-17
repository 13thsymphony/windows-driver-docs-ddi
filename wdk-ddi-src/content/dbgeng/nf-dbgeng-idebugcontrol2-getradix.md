---
UID: NF:dbgeng.IDebugControl2.GetRadix
title: IDebugControl2::GetRadix method
author: windows-driver-content
description: The GetRadix method returns the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.
old-location: debugger\getradix.htm
old-project: debugger
ms.assetid: eae478e1-f70c-4344-a6e0-982a668c1f5d
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetRadix, dbgeng/IDebugControl::GetRadix, IDebugControl3 interface [Windows Debugging], GetRadix method, GetRadix method [Windows Debugging], IDebugControl3 interface, dbgeng/IDebugControl2::GetRadix, GetRadix method [Windows Debugging], IDebugControl interface, GetRadix method [Windows Debugging], IDebugControl2 interface, dbgeng/IDebugControl3::GetRadix, IDebugControl::GetRadix, IDebugControl2, GetRadix method [Windows Debugging], IDebugControl2::GetRadix, IDebugControl3::GetRadix, IDebugControl_3f4cb732-868a-4944-bcd9-dd1f221824df.xml, IDebugControl2 interface [Windows Debugging], GetRadix method, IDebugControl, IDebugControl interface [Windows Debugging], GetRadix method, debugger.getradix
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl.GetRadix
-	IDebugControl2.GetRadix
-	IDebugControl3.GetRadix
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetRadix method
The <b>GetRadix</b> method returns the default radix (number base) used by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> when it evaluates and displays MASM expressions, and when it displays symbol information.

## Syntax

````
HRESULT GetRadix(
  [out] PULONG Radix
);
````

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
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556770">SetRadix</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552287">n (Set Number Base)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetRadix method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>