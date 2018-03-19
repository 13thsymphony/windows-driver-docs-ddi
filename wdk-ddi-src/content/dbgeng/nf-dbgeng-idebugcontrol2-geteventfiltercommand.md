---
UID: NF:dbgeng.IDebugControl2.GetEventFilterCommand
title: IDebugControl2::GetEventFilterCommand method
author: windows-driver-content
description: The GetEventFilterCommand method returns the debugger command that the engine will execute when a specified event occurs.
old-location: debugger\geteventfiltercommand.htm
old-project: debugger
ms.assetid: ea88d1de-70c1-424a-a3a0-cce46cc3fe39
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetEventFilterCommand method [Windows Debugging], GetEventFilterCommand method [Windows Debugging], IDebugControl interface, GetEventFilterCommand method [Windows Debugging], IDebugControl2 interface, GetEventFilterCommand method [Windows Debugging], IDebugControl3 interface, GetEventFilterCommand,IDebugControl2.GetEventFilterCommand, IDebugControl interface [Windows Debugging], GetEventFilterCommand method, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetEventFilterCommand method, IDebugControl2::GetEventFilterCommand, IDebugControl3 interface [Windows Debugging], GetEventFilterCommand method, IDebugControl3::GetEventFilterCommand, IDebugControl::GetEventFilterCommand, IDebugControl_a0acf45f-8741-48a0-9eb0-f8a9aa55c476.xml, dbgeng/IDebugControl2::GetEventFilterCommand, dbgeng/IDebugControl3::GetEventFilterCommand, dbgeng/IDebugControl::GetEventFilterCommand, debugger.geteventfiltercommand
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
-	IDebugControl.GetEventFilterCommand
-	IDebugControl2.GetEventFilterCommand
-	IDebugControl3.GetEventFilterCommand
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetEventFilterCommand method
The <b>GetEventFilterCommand</b>  method returns the debugger command that the engine will execute when a specified event occurs.

## Syntax

````
HRESULT GetEventFilterCommand(
  [in]            ULONG  Index,
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG CommandSize
);
````

## Parameters

`Index`

Specifies the index of the event filter.  <i>Index</i> can take any value between zero and one less than the total number of event filters returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547899">GetNumberEventFilters</a> (inclusive).  For more information about the index of the filters, see Index and Exception Code.

`Buffer`

Receives the debugger command that the engine will execute when the event occurs.

`BufferSize`

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.

`CommandSize`

Receives the size in characters of the command.  If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.


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

For more information about event filters, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556678">SetEventFilterCommand</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546653">GetExceptionFilterSecondCommand</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>