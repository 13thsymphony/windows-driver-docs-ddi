---
UID: NF:dbgeng.IDebugControl.SetNotifyEventHandle
title: IDebugControl::SetNotifyEventHandle method
author: windows-driver-content
description: The SetNotifyEventHandle method sets the event that will be signaled after the next exception in a target.
old-location: debugger\setnotifyeventhandle.htm
old-project: debugger
ms.assetid: 0c0059a7-4b0f-4b74-b543-ad5904d40033
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugControl, IDebugControl interface [Windows Debugging], SetNotifyEventHandle method, IDebugControl2 interface [Windows Debugging], SetNotifyEventHandle method, IDebugControl2::SetNotifyEventHandle, IDebugControl3 interface [Windows Debugging], SetNotifyEventHandle method, IDebugControl3::SetNotifyEventHandle, IDebugControl::SetNotifyEventHandle, IDebugControl_9934efa7-aed4-4706-8885-71d78f6950a8.xml, SetNotifyEventHandle method [Windows Debugging], SetNotifyEventHandle method [Windows Debugging], IDebugControl interface, SetNotifyEventHandle method [Windows Debugging], IDebugControl2 interface, SetNotifyEventHandle method [Windows Debugging], IDebugControl3 interface, SetNotifyEventHandle,IDebugControl.SetNotifyEventHandle, dbgeng/IDebugControl2::SetNotifyEventHandle, dbgeng/IDebugControl3::SetNotifyEventHandle, dbgeng/IDebugControl::SetNotifyEventHandle, debugger.setnotifyeventhandle
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
-	IDebugControl.SetNotifyEventHandle
-	IDebugControl2.SetNotifyEventHandle
-	IDebugControl3.SetNotifyEventHandle
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugControl::SetNotifyEventHandle method
The <b>SetNotifyEventHandle</b> method sets the event that will be signaled after the next <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a> in a target.

## Syntax

```
HRESULT SetNotifyEventHandle(
  ULONG64 Handle
);
```

## Parameters

`Handle`

Specifies the handle of the event to signal.  If <i>Handle</i> is <b>NULL</b>, no event will be signaled.


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

After setting the event to signal, and after the next exception occurs in a target, when the engine resumes execution in the target, the event will be signaled.

The event will only be signaled once.  After it has been signaled, <b>GetNotifyEventHandle</b> will return <b>NULL</b>, unless this method is called to set another event to signal.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556739">SetNotifyEventHandle</a>