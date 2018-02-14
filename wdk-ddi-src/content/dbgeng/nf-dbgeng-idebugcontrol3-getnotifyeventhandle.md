---
UID: NF:dbgeng.IDebugControl3.GetNotifyEventHandle
title: IDebugControl3::GetNotifyEventHandle method
author: windows-driver-content
description: The GetNotifyEventHandle method receives the handle of the event that will be signaled after the next exception in a target.
old-location: debugger\getnotifyeventhandle.htm
old-project: debugger
ms.assetid: a949a583-1ee1-4538-9117-4ad1482e8bc8
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugControl::GetNotifyEventHandle, IDebugControl2, IDebugControl3::GetNotifyEventHandle, IDebugControl2::GetNotifyEventHandle, GetNotifyEventHandle method [Windows Debugging], IDebugControl interface, GetNotifyEventHandle method [Windows Debugging], debugger.getnotifyeventhandle, IDebugControl interface [Windows Debugging], GetNotifyEventHandle method, IDebugControl3, IDebugControl::GetNotifyEventHandle, IDebugControl, IDebugControl_73931ad2-ace6-4d38-ad22-c322f2e3c13c.xml, IDebugControl3 interface [Windows Debugging], GetNotifyEventHandle method, dbgeng/IDebugControl2::GetNotifyEventHandle, GetNotifyEventHandle method [Windows Debugging], IDebugControl3 interface, IDebugControl2 interface [Windows Debugging], GetNotifyEventHandle method, GetNotifyEventHandle, GetNotifyEventHandle method [Windows Debugging], IDebugControl2 interface, dbgeng/IDebugControl3::GetNotifyEventHandle
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
-	IDebugControl.GetNotifyEventHandle
-	IDebugControl2.GetNotifyEventHandle
-	IDebugControl3.GetNotifyEventHandle
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetNotifyEventHandle method
The <b>GetNotifyEventHandle</b> method receives the handle of the event that will be signaled after the next <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a> in a target.

## Syntax

````
HRESULT GetNotifyEventHandle(
  [out] PULONG64 Handle
);
````

## Parameters

`Handle`

Receives the handle of the event that will be signaled.  If <i>Handle</i> is <b>NULL</b>, no event will be signaled.


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

If an event to be signaled was set and an exception occurs in a target, when the engine resumes execution in the target again, the event will be signaled.

The event will only be signaled once.  After it has been signaled, this method will return <b>NULL</b> to <i>Handle</i>, unless <a href="https://msdn.microsoft.com/library/windows/hardware/ff556739">SetNotifyEventHandle</a> is called to set another event to signal.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556739">SetNotifyEventHandle</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetNotifyEventHandle method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>