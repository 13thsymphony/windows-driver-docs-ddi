---
UID: NF:dbgeng.IDebugControl.GetExecutionStatus
title: IDebugControl::GetExecutionStatus method
author: windows-driver-content
description: The GetExecutionStatus method returns information about the execution status of the debugger engine.
old-location: debugger\getexecutionstatus.htm
old-project: debugger
ms.assetid: 58352577-9ed9-4fc6-9cc7-dabcf4f77ad9
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugControl::GetExecutionStatus, GetExecutionStatus method [Windows Debugging], IDebugControl3 interface, IDebugControl3 interface [Windows Debugging], GetExecutionStatus method, GetExecutionStatus method [Windows Debugging], IDebugControl interface [Windows Debugging], GetExecutionStatus method, GetExecutionStatus method [Windows Debugging], IDebugControl interface, dbgeng/IDebugControl2::GetExecutionStatus, IDebugControl, dbgeng/IDebugControl3::GetExecutionStatus, GetExecutionStatus, IDebugControl3::GetExecutionStatus, IDebugControl_0e47a42b-f980-4c4b-b8b3-8d795498e5d5.xml, debugger.getexecutionstatus, IDebugControl::GetExecutionStatus, GetExecutionStatus method [Windows Debugging], IDebugControl2 interface, IDebugControl2::GetExecutionStatus, IDebugControl2 interface [Windows Debugging], GetExecutionStatus method
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
-	IDebugControl.GetExecutionStatus
-	IDebugControl2.GetExecutionStatus
-	IDebugControl3.GetExecutionStatus
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetExecutionStatus method
The <b>GetExecutionStatus</b> method returns information about the execution status of the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.

## Syntax

````
HRESULT GetExecutionStatus(
  [out] PULONG Status
);
````

## Parameters

`Status`

Receives the execution status.  This will be set to one of the values in the following table. Note that the description of these values differs slightly from the description in <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a>.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_STATUS_NO_DEBUGGEE

</td>
<td>
The engine is not attached to a target.

</td>
</tr>
<tr>
<td>
DEBUG_STATUS_STEP_OVER

</td>
<td>
The target is currently executing a single instruction.  If that instruction is a subroutine call, the entire call will be executed.

</td>
</tr>
<tr>
<td>
DEBUG_STATUS_STEP_INTO

</td>
<td>
The target is currently executing a single instruction.

</td>
</tr>
<tr>
<td>
DEBUG_STATUS_STEP_BRANCH

</td>
<td>
The target is currently running until it encounters a branch instruction.

</td>
</tr>
<tr>
<td>
DEBUG_STATUS_GO

</td>
<td>
The target is currently running normally.  It will continue normal execution until an event occurs.

</td>
</tr>
<tr>
<td>
DEBUG_STATUS_BREAK

</td>
<td>
The target is not running.

</td>
</tr>
</table>


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

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556693">SetExecutionStatus</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetExecutionStatus method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>