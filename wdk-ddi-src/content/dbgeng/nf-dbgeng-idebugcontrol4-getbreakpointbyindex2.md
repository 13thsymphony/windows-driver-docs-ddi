---
UID: NF:dbgeng.IDebugControl4.GetBreakpointByIndex2
title: IDebugControl4::GetBreakpointByIndex2 method
author: windows-driver-content
description: The GetBreakpointByIndex2 method returns the breakpoint located at the specified index.
old-location: debugger\getbreakpointbyindex2.htm
old-project: debugger
ms.assetid: 3487addb-e196-4295-95fc-0590802e766a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetBreakpointByIndex2 method [Windows Debugging], dbgeng/IDebugControl4::GetBreakpointByIndex2, GetBreakpointByIndex2 method [Windows Debugging], IDebugControl4 interface, IDebugControl4, GetBreakpointByIndex2, IDebugControl4::GetBreakpointByIndex2, IDebugControl4 interface [Windows Debugging], GetBreakpointByIndex2 method, debugger.getbreakpointbyindex2
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
-	IDebugControl4.GetBreakpointByIndex2
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetBreakpointByIndex2 method
The <b>GetBreakpointByIndex2</b>  method returns the breakpoint located at the specified index.

## Syntax

````
HRESULT GetBreakpointByIndex2(
  [in]  ULONG              Index,
  [out] PDEBUG_BREAKPOINT2 *Bp
);
````

## Parameters

`Index`

Specifies the zero-based index of the breakpoint to return.  This is specific to the current process.  The value of <i>Index</i> should be between zero and the total number of breakpoints minus one. The total number of breakpoints can be determined by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547880">GetNumberBreakpoints</a>.

`Bp`

Receives the returned breakpoint.


## Return Value

This method can also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No breakpoint was found with the given index, or the breakpoint with the given index is private.

</td>
</tr>
</table>

## Remarks

The index and returned breakpoint are specific to the current process.  The same index will return a different breakpoint if the current process is changed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547880">GetNumberBreakpoints</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetBreakpointByIndex2 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>