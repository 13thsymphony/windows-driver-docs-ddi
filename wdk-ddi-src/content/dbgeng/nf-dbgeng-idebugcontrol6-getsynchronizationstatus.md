---
UID: NF:dbgeng.IDebugControl6.GetSynchronizationStatus
title: IDebugControl6::GetSynchronizationStatus method
author: windows-driver-content
description: The GetSynchronizationStatus method returns information about the synchronization status of the debugger engine.
old-location: debugger\idebugcontrol6_getsynchronizationstatus.htm
old-project: debugger
ms.assetid: 94DD7FBF-2D4F-4DD9-A49E-A9FA494BF995
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetSynchronizationStatus method [Windows Debugging], GetSynchronizationStatus method [Windows Debugging], IDebugControl6 interface, GetSynchronizationStatus,IDebugControl6.GetSynchronizationStatus, IDebugControl6, IDebugControl6 interface [Windows Debugging], GetSynchronizationStatus method, IDebugControl6::GetSynchronizationStatus, dbgeng/IDebugControl6::GetSynchronizationStatus, debugger.idebugcontrol6_getsynchronizationstatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: 
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
-	IDebugControl6.GetSynchronizationStatus
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugControl6::GetSynchronizationStatus method
The GetSynchronizationStatus method returns information about the synchronization status of the debugger engine.

## Syntax

```
HRESULT GetSynchronizationStatus(
  PULONG SendsAttempted,
  PULONG SecondsSinceLastResponse
);
```

## Parameters

`SendsAttempted`

The number of packet sends that have been attempted by the current debugger-engine kernel transport mechanism. This number will be incremented if engine did not receive a packet "ACK" for the last packet sent by the engine to the target.

`SecondsSinceLastResponse`

The number of seconds since the last response.


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

When the client object connects to a session, the most recent output from the session is sent to the client. If the session is currently waiting on input, the client object is given the opportunity to provide input. Thus, the client object synchronizes with the session's input and output.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn818568">IDebugControl6</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558852">Synchronizing with the Target Computer</a>