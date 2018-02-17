---
UID: NF:dbgeng.IDebugClient4.EndSession
title: IDebugClient4::EndSession method
author: windows-driver-content
description: The EndSession method ends the current debugger session.
old-location: debugger\endsession.htm
old-project: debugger
ms.assetid: 521a0e4a-99c6-4ad4-886d-3fff9855e1fd
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient4::EndSession, dbgeng/IDebugClient2::EndSession, EndSession, IDebugClient3, IDebugClient, dbgeng/IDebugClient4::EndSession, dbgeng/IDebugClient3::EndSession, EndSession method [Windows Debugging], IDebugClient5 interface, dbgeng/IDebugClient::EndSession, IDebugClient2, EndSession method [Windows Debugging], IDebugClient interface, IDebugClient3 interface [Windows Debugging], EndSession method, EndSession method [Windows Debugging], IDebugClient3 interface, IDebugClient5::EndSession, IDebugClient4 interface [Windows Debugging], EndSession method, EndSession method [Windows Debugging], IDebugClient2 interface, debugger.endsession, IDebugClient::EndSession, EndSession method [Windows Debugging], IDebugClient4 interface, IDebugClient_b3243254-eb98-4ee6-8dc9-92fe4c998500.xml, IDebugClient2::EndSession, IDebugClient4, IDebugClient3::EndSession, IDebugClient2 interface [Windows Debugging], EndSession method, IDebugClient5 interface [Windows Debugging], EndSession method, dbgeng/IDebugClient5::EndSession, IDebugClient interface [Windows Debugging], EndSession method, EndSession method [Windows Debugging]
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
-	IDebugClient.EndSession
-	IDebugClient2.EndSession
-	IDebugClient3.EndSession
-	IDebugClient4.EndSession
-	IDebugClient5.EndSession
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# EndSession method
The <b>EndSession</b> method ends the current debugger session.

## Syntax

````
HRESULT EndSession(
  [in] ULONG Flags
);
````

## Parameters

`Flags`

Specifies how to end the session.  <i>Flags</i> can be one of the following values:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_END_PASSIVE

</td>
<td>
Perform cleanup for the session.

</td>
</tr>
<tr>
<td>
DEBUG_END_ACTIVE_TERMINATE

</td>
<td>
Attempt to terminate all user-mode targets before performing cleanup for the session.

</td>
</tr>
<tr>
<td>
DEBUG_END_ACTIVE_DETACH

</td>
<td>
Attempt to disconnect from all targets before performing cleanup for the session.

</td>
</tr>
<tr>
<td>
DEBUG_END_REENTRANT

</td>
<td>
Perform only the cleanup that doesn't require acquiring locks.  See Remarks section for details.

</td>
</tr>
<tr>
<td>
DEBUG_END_DISCONNECT

</td>
<td>
Do not end the session.  Disconnect the client from the session and disable the client.

This flag is intended for when remote clients disconnect.  It generates a server message about the disconnection.

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

This method may be called at any time with <i>Flags</i> set to DEBUG_END_REENTRANT.  If, for example, the application needs to exit but another thread is using the engine, this method can be used to perform as much cleanup as possible.

Using DEBUG_END_REENTRANT may leave the engine in an indeterminate state. If this flag is used, no subsequent calls should be made to the engine.

For more information about debugger sessions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |