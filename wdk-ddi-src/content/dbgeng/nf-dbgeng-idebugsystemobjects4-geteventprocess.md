---
UID: NF:dbgeng.IDebugSystemObjects4.GetEventProcess
title: IDebugSystemObjects4::GetEventProcess method
author: windows-driver-content
description: The GetEventProcess method returns the engine process ID for the process on which the last event occurred.
old-location: debugger\geteventprocess.htm
old-project: debugger
ms.assetid: 77cf1995-f3f3-4a03-bba7-9df230a10da0
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects interface [Windows Debugging], GetEventProcess method, GetEventProcess method [Windows Debugging], IDebugSystemObjects interface, IDebugSystemObjects3::GetEventProcess, GetEventProcess, IDebugSystemObjects2::GetEventProcess, IDebugSystemObjects3 interface [Windows Debugging], GetEventProcess method, dbgeng/IDebugSystemObjects3::GetEventProcess, IDebugSystemObjects2 interface [Windows Debugging], GetEventProcess method, GetEventProcess method [Windows Debugging], dbgeng/IDebugSystemObjects4::GetEventProcess, IDebugSystemObjects4, IDebugSystemObjects::GetEventProcess, IDebugSystemObjects4 interface [Windows Debugging], GetEventProcess method, GetEventProcess method [Windows Debugging], IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects2::GetEventProcess, debugger.geteventprocess, GetEventProcess method [Windows Debugging], IDebugSystemObjects3 interface, dbgeng/IDebugSystemObjects::GetEventProcess, IDebugSystemObjects4::GetEventProcess, IDebugSystemObjects_04f445d4-e407-4e0c-bd1b-9570ed4f0433.xml, GetEventProcess method [Windows Debugging], IDebugSystemObjects2 interface
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
-	IDebugSystemObjects.GetEventProcess
-	IDebugSystemObjects2.GetEventProcess
-	IDebugSystemObjects3.GetEventProcess
-	IDebugSystemObjects4.GetEventProcess
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetEventProcess method
The <b>GetEventProcess</b> method returns the engine process ID for the process on which the last event occurred.

## Syntax

````
HRESULT GetEventProcess(
  [out] PULONG Id
);
````

## Parameters

`Id`

Receives the engine process ID.


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

In kernel-mode debugging, the engine process ID for the virtual process representing the kernel is returned.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details about debugger engine events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |