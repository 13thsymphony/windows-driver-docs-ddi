---
UID: NF:dbgeng.IDebugSystemObjects2.GetProcessIdsByIndex
title: IDebugSystemObjects2::GetProcessIdsByIndex method
author: windows-driver-content
description: The GetProcessIdsByIndex method returns the engine process ID and system process ID for the specified processes in the current target.
old-location: debugger\getprocessidsbyindex.htm
old-project: debugger
ms.assetid: 2ae042c5-9c2a-4de4-817c-c9b97f979684
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects2::GetProcessIdsByIndex, IDebugSystemObjects3::GetProcessIdsByIndex, IDebugSystemObjects_45309dcc-89bd-44a1-bafa-baabd10d54b0.xml, GetProcessIdsByIndex method [Windows Debugging], IDebugSystemObjects4 interface, IDebugSystemObjects::GetProcessIdsByIndex, IDebugSystemObjects4 interface [Windows Debugging], GetProcessIdsByIndex method, GetProcessIdsByIndex method [Windows Debugging], GetProcessIdsByIndex method [Windows Debugging], IDebugSystemObjects2 interface, dbgeng/IDebugSystemObjects::GetProcessIdsByIndex, IDebugSystemObjects2 interface [Windows Debugging], GetProcessIdsByIndex method, GetProcessIdsByIndex method [Windows Debugging], IDebugSystemObjects3 interface, IDebugSystemObjects3 interface [Windows Debugging], GetProcessIdsByIndex method, IDebugSystemObjects, IDebugSystemObjects interface [Windows Debugging], GetProcessIdsByIndex method, dbgeng/IDebugSystemObjects2::GetProcessIdsByIndex, dbgeng/IDebugSystemObjects4::GetProcessIdsByIndex, GetProcessIdsByIndex method [Windows Debugging], IDebugSystemObjects interface, debugger.getprocessidsbyindex, IDebugSystemObjects4::GetProcessIdsByIndex, dbgeng/IDebugSystemObjects3::GetProcessIdsByIndex, IDebugSystemObjects2, GetProcessIdsByIndex
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
-	IDebugSystemObjects.GetProcessIdsByIndex
-	IDebugSystemObjects2.GetProcessIdsByIndex
-	IDebugSystemObjects3.GetProcessIdsByIndex
-	IDebugSystemObjects4.GetProcessIdsByIndex
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetProcessIdsByIndex method
The <b>GetProcessIdsByIndex</b> method returns the engine process ID and system process ID for the specified <a href="https://msdn.microsoft.com/6182ca34-ee5e-47e9-82fe-29266397e3a8">processes</a> in the current target.

## Syntax

````
HRESULT GetProcessIdsByIndex(
  [in]            ULONG  Start,
  [in]            ULONG  Count,
  [out, optional] PULONG Ids,
  [out, optional] PULONG SysIds
);
````

## Parameters

`Start`

Specifies the index of the first process whose ID is requested.

`Count`

Specifies the number of processes whose IDs are requested.

`Ids`

Receives the engine process IDs.  If <i>Ids</i> is <b>NULL</b>, this information is not returned; otherwise, <i>Ids</i> is treated as an array of <i>Count</i> ULONG values.

`SysIds`

Receives the system process IDs.  If <i>SysIds</i> is <b>NULL</b>, this information is not returned; otherwise, <i>SysIds</i> is treated as an array of <i>Count</i> ULONG values.


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

The index of the first process is zero.  The index of the last process is the number of processes returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547946">GetNumberProcesses</a> minus one.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |