---
UID: NF:dbgeng.IDebugControl3.GetBreakpointById
title: IDebugControl3::GetBreakpointById method
author: windows-driver-content
description: The GetBreakpointById method returns the breakpoint with the specified breakpoint ID.
old-location: debugger\getbreakpointbyid.htm
old-project: debugger
ms.assetid: 6873609d-7f5a-474d-8b48-fee9f93c812b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetBreakpointById method [Windows Debugging], GetBreakpointById method [Windows Debugging], IDebugControl interface, GetBreakpointById method [Windows Debugging], IDebugControl2 interface, GetBreakpointById method [Windows Debugging], IDebugControl3 interface, GetBreakpointById,IDebugControl3.GetBreakpointById, IDebugControl interface [Windows Debugging], GetBreakpointById method, IDebugControl2 interface [Windows Debugging], GetBreakpointById method, IDebugControl2::GetBreakpointById, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetBreakpointById method, IDebugControl3::GetBreakpointById, IDebugControl::GetBreakpointById, IDebugControl_641f8e32-6c08-4b63-89c6-877b52a86ab2.xml, dbgeng/IDebugControl2::GetBreakpointById, dbgeng/IDebugControl3::GetBreakpointById, dbgeng/IDebugControl::GetBreakpointById, debugger.getbreakpointbyid
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl.GetBreakpointById
-	IDebugControl2.GetBreakpointById
-	IDebugControl3.GetBreakpointById
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetBreakpointById method
The <b>GetBreakpointById</b>  method returns the breakpoint with the specified breakpoint ID.

## Syntax

````
HRESULT GetBreakpointById(
  [in]  ULONG             Id,
  [out] PDEBUG_BREAKPOINT *Bp
);
````

## Parameters

`Id`

Specifies the breakpoint ID of the breakpoint to return.

`Bp`

Receives the breakpoint.


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
No breakpoint was found with the given ID, or the breakpoint with the specified ID does not belong to the current process, or the breakpoint with the given ID is private (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546791">GetFlags</a>).

</td>
</tr>
</table>

## Remarks

If the specified breakpoint does not belong to the current process, the method will fail.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetBreakpointById method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>