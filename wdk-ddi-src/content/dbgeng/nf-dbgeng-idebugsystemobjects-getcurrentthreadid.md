---
UID: NF:dbgeng.IDebugSystemObjects.GetCurrentThreadId
title: IDebugSystemObjects::GetCurrentThreadId method
author: windows-driver-content
description: The GetCurrentThreadId method returns the engine thread ID for the current thread.
old-location: debugger\getcurrentthreadid.htm
old-project: Debugger
ms.assetid: 7062c962-2e82-40e3-81ea-97ac0948e501
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugSystemObjects::GetCurrentThreadId, debugger.getcurrentthreadid, dbgeng/IDebugSystemObjects::GetCurrentThreadId, IDebugSystemObjects4::GetCurrentThreadId, GetCurrentThreadId method [Windows Debugging], IDebugSystemObjects interface [Windows Debugging], GetCurrentThreadId method, GetCurrentThreadId method [Windows Debugging], IDebugSystemObjects interface, IDebugSystemObjects2::GetCurrentThreadId, dbgeng/IDebugSystemObjects2::GetCurrentThreadId, GetCurrentThreadId, IDebugSystemObjects, dbgeng/IDebugSystemObjects4::GetCurrentThreadId, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentThreadId method, IDebugSystemObjects_e40e3ab8-b03d-4b1e-805b-ad8ba51ea1c5.xml, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentThreadId method, GetCurrentThreadId method [Windows Debugging], IDebugSystemObjects2 interface, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentThreadId method, dbgeng/IDebugSystemObjects3::GetCurrentThreadId, IDebugSystemObjects3::GetCurrentThreadId, GetCurrentThreadId method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentThreadId method [Windows Debugging], IDebugSystemObjects4 interface
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
-	IDebugSystemObjects.GetCurrentThreadId
-	IDebugSystemObjects2.GetCurrentThreadId
-	IDebugSystemObjects3.GetCurrentThreadId
-	IDebugSystemObjects4.GetCurrentThreadId
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetCurrentThreadId method
The <b>GetCurrentThreadId</b> method returns the engine thread ID for the current thread.

## Syntax

````
HRESULT GetCurrentThreadId(
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

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |