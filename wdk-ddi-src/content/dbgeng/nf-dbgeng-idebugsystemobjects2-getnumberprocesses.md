---
UID: NF:dbgeng.IDebugSystemObjects2.GetNumberProcesses
title: IDebugSystemObjects2::GetNumberProcesses method
author: windows-driver-content
description: The GetNumberProcesses method returns the number of processes for the current target.
old-location: debugger\getnumberprocesses.htm
old-project: debugger
ms.assetid: bf0c750f-0e29-42d9-a127-953e3d49b969
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugSystemObjects3::GetNumberProcesses, debugger.getnumberprocesses, IDebugSystemObjects2::GetNumberProcesses, GetNumberProcesses method [Windows Debugging], IDebugSystemObjects interface, GetNumberProcesses method [Windows Debugging], IDebugSystemObjects3 interface, IDebugSystemObjects::GetNumberProcesses, IDebugSystemObjects3 interface [Windows Debugging], GetNumberProcesses method, IDebugSystemObjects2 interface [Windows Debugging], GetNumberProcesses method, IDebugSystemObjects3::GetNumberProcesses, dbgeng/IDebugSystemObjects2::GetNumberProcesses, GetNumberProcesses method [Windows Debugging], IDebugSystemObjects2 interface, GetNumberProcesses method [Windows Debugging], IDebugSystemObjects4 interface, IDebugSystemObjects_28914631-9658-462c-8234-f48bb85efdf6.xml, GetNumberProcesses method [Windows Debugging], dbgeng/IDebugSystemObjects::GetNumberProcesses, IDebugSystemObjects4 interface [Windows Debugging], GetNumberProcesses method, GetNumberProcesses, IDebugSystemObjects2, IDebugSystemObjects interface [Windows Debugging], GetNumberProcesses method, IDebugSystemObjects4::GetNumberProcesses, IDebugSystemObjects, dbgeng/IDebugSystemObjects4::GetNumberProcesses
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
-	IDebugSystemObjects.GetNumberProcesses
-	IDebugSystemObjects2.GetNumberProcesses
-	IDebugSystemObjects3.GetNumberProcesses
-	IDebugSystemObjects4.GetNumberProcesses
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetNumberProcesses method
The <b>GetNumberProcesses</b> method returns the number of <a href="https://msdn.microsoft.com/6182ca34-ee5e-47e9-82fe-29266397e3a8">processes</a> for the current target.

## Syntax

````
HRESULT GetNumberProcesses(
  [out] PULONG Number
);
````

## Parameters

`Number`

Receives the number of processes.


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

In kernel-mode debugging, there is only a single virtual process representing the kernel.

In user-mode debugging, the number of processes changes with the create-process and exit-process debugging <a href="https://msdn.microsoft.com/library/windows/hardware/ff543067">events</a>.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |