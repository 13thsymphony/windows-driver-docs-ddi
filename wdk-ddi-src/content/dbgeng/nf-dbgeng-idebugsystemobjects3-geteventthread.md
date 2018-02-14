---
UID: NF:dbgeng.IDebugSystemObjects3.GetEventThread
title: IDebugSystemObjects3::GetEventThread method
author: windows-driver-content
description: The GetEventThread method returns the engine thread ID for the thread on which the last event occurred.
old-location: debugger\geteventthread.htm
old-project: debugger
ms.assetid: 7a28c9bd-480e-4864-b7ff-9ff0dc1d04ad
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetEventThread method [Windows Debugging], IDebugSystemObjects2 interface, GetEventThread method [Windows Debugging], IDebugSystemObjects interface, GetEventThread, IDebugSystemObjects4 interface [Windows Debugging], GetEventThread method, IDebugSystemObjects3::GetEventThread, IDebugSystemObjects_2074b9ad-a761-42fd-93ed-4774c2ddf3a5.xml, IDebugSystemObjects3 interface [Windows Debugging], GetEventThread method, debugger.geteventthread, dbgeng/IDebugSystemObjects::GetEventThread, GetEventThread method [Windows Debugging], IDebugSystemObjects3 interface, IDebugSystemObjects interface [Windows Debugging], GetEventThread method, IDebugSystemObjects::GetEventThread, dbgeng/IDebugSystemObjects2::GetEventThread, GetEventThread method [Windows Debugging], IDebugSystemObjects4::GetEventThread, IDebugSystemObjects2::GetEventThread, GetEventThread method [Windows Debugging], IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects4::GetEventThread, dbgeng/IDebugSystemObjects3::GetEventThread, IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], GetEventThread method, IDebugSystemObjects3, IDebugSystemObjects
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
-	IDebugSystemObjects.GetEventThread
-	IDebugSystemObjects2.GetEventThread
-	IDebugSystemObjects3.GetEventThread
-	IDebugSystemObjects4.GetEventThread
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetEventThread method
The <b>GetEventThread</b> method returns the engine thread ID for the thread on which the last event occurred.

## Syntax

````
HRESULT GetEventThread(
  [out] PULONG Id
);
````

## Parameters

`Id`

Receives the engine thread ID.


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

In kernel-mode debugging, the engine thread ID for the virtual thread representing the processor on which the event occurred is returned.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details about debugger engine events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |