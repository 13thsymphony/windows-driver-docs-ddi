---
UID: NF:dbgeng.IDebugControl2.SetExecutionStatus
title: IDebugControl2::SetExecutionStatus method
author: windows-driver-content
description: The SetExecutionStatus method requests that the debugger engine enter an executable state. Actual execution will not occur until the next time WaitForEvent is called.
old-location: debugger\setexecutionstatus.htm
old-project: debugger
ms.assetid: f3468fe5-31b4-4bf6-b0e3-ee27ecfd8e06
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugControl interface [Windows Debugging], SetExecutionStatus method, IDebugControl2, IDebugControl2 interface [Windows Debugging], SetExecutionStatus method, IDebugControl2::SetExecutionStatus, IDebugControl3 interface [Windows Debugging], SetExecutionStatus method, IDebugControl3::SetExecutionStatus, IDebugControl::SetExecutionStatus, IDebugControl_b89bf576-8a07-49a8-8373-0b915300d36a.xml, SetExecutionStatus method [Windows Debugging], SetExecutionStatus method [Windows Debugging], IDebugControl interface, SetExecutionStatus method [Windows Debugging], IDebugControl2 interface, SetExecutionStatus method [Windows Debugging], IDebugControl3 interface, SetExecutionStatus,IDebugControl2.SetExecutionStatus, dbgeng/IDebugControl2::SetExecutionStatus, dbgeng/IDebugControl3::SetExecutionStatus, dbgeng/IDebugControl::SetExecutionStatus, debugger.setexecutionstatus
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
-	IDebugControl.SetExecutionStatus
-	IDebugControl2.SetExecutionStatus
-	IDebugControl3.SetExecutionStatus
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# SetExecutionStatus method
The <b>SetExecutionStatus</b> method requests that the debugger engine enter an executable state.  Actual execution will not occur until the next time <a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a> is called.

## Syntax

````
HRESULT SetExecutionStatus(
  [in] ULONG Status
);
````

## Parameters

`Status`

Specifies the mode for the engine to use when executing.  Possible values are those values in the table in <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> whose precedence lies between DEBUG_STATUS_GO and DEBUG_STATUS_STEP_INTO.


## Return Value

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
Something prevented the execution of this method. Possible causes include: there is no current target, there is an outstanding request for input, or execution is not supported in the current target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_ACCESSDENIED</b></dt>
</dl>
</td>
<td width="60%">
The target is already executing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No target can generate any more events.

</td>
</tr>
</table>

## Remarks

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546675">GetExecutionStatus</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>