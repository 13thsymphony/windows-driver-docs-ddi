---
UID : NF:dbgeng.IDebugEventCallbacksWide.SessionStatus
title : IDebugEventCallbacksWide::SessionStatus method
author : windows-driver-content
description : The SessionStatus callback method is called by the engine when a change occurs in the debugger session.
old-location : debugger\idebugeventcallbackswide_sessionstatus.htm
old-project : debugger
ms.assetid : cc3ed4ef-5e2d-4865-8d6f-b140d6b5d7af
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugEventCallbacksWide::SessionStatus, IDebugEventCallbacksWide, dbgeng/IDebugEventCallbacksWide::SessionStatus, SessionStatus, SessionStatus method [Windows Debugging], SessionStatus method [Windows Debugging], IDebugEventCallbacksWide interface, debugger.idebugeventcallbackswide_sessionstatus, IDebugEventCallbacksWide interface [Windows Debugging], SessionStatus method
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : dbgeng.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# SessionStatus method
The <b>SessionStatus</b> callback method is called by the engine when a change occurs in the debugger session.

## Syntax

````
HRESULT SessionStatus(
  [in] ULONG Status
);
````

## Parameters

`Status`

Specifies the new status of the debugger session.  The following table describes the possible values.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_SESSION_ACTIVE

</td>
<td>
A debugger session has started.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_END_SESSION_ACTIVE_TERMINATE

</td>
<td>
The session was ended by sending DEBUG_END_ACTIVE_TERMINATE to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543004">EndSession</a>.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_END_SESSION_ACTIVE_DETACH

</td>
<td>
The session was ended by sending DEBUG_END_ACTIVE_DETACH to <b>EndSession</b>.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_END_SESSION_PASSIVE

</td>
<td>
The session was ended by sending DEBUG_END_PASSIVE to <b>EndSession</b>.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_END

</td>
<td>
The  target ran to completion, ending the session.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_REBOOT

</td>
<td>
The  target computer rebooted, ending the session.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_HIBERNATE

</td>
<td>
The  target computer went into hibernation, ending the session.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_FAILURE

</td>
<td>
The engine was unable to continue the session.

</td>
</tr>
</table>


## Return Value

This method's return value is ignored by the engine.

## Remarks

This method is only called by the engine if the DEBUG_EVENT_SESSION_STATUS flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550625">IDebugEventCallbacksWide::GetInterestMask</a>.

After the engine has notified all the event callbacks of the change in the session status, it will also notify any loaded <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">extensions</a> that export the <a href="..\dbgeng\nc-dbgeng-pdebug_extension_notify.md">DebugExtensionNotify</a> callback method.  The value that it passes to the extensions depends on the value of <i>Status</i>.  If <i>Status</i> is DEBUG_SESSION_ACTIVE, it passes DEBUG_SESSION_ACTIVE; otherwise, it passes DEBUG_SESSION_INACTIVE.

In the DEBUG_SESSION_ACTIVE case, the engine follows the debugger session change notification with a target state change notification by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550573">IDebugEventCallbacksWide::ChangeDebuggeeState</a> on the event callbacks and passing DEBUG_CDS_ALL in the <i>Flags</i> parameter.  In all other cases, the engine precedes this notification with an engine state change notification by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550578">IDebugEventCallbacksWide::ChangeEngineState</a> on the event callbacks and passing DEBUG_CES_EXECUTION_STATUS in the <i>Flags</i> parameter.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about debugger sessions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |