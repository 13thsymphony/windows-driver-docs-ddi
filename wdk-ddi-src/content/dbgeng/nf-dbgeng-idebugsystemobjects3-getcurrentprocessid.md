---
UID: NF:dbgeng.IDebugSystemObjects3.GetCurrentProcessId
title: IDebugSystemObjects3::GetCurrentProcessId method
author: windows-driver-content
description: The GetCurrentProcessId method returns the engine process ID for the current process.
old-location: debugger\getcurrentprocessid.htm
old-project: debugger
ms.assetid: 5b256ccb-8f03-4936-8e03-9955c81384a5
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.getcurrentprocessid, GetCurrentProcessId method [Windows Debugging], IDebugSystemObjects interface, GetCurrentProcessId, IDebugSystemObjects3::GetCurrentProcessId, dbgeng/IDebugSystemObjects2::GetCurrentProcessId, GetCurrentProcessId method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentProcessId method [Windows Debugging], IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects::GetCurrentProcessId, GetCurrentProcessId method [Windows Debugging], IDebugSystemObjects2 interface, IDebugSystemObjects2::GetCurrentProcessId, dbgeng/IDebugSystemObjects4::GetCurrentProcessId, IDebugSystemObjects4::GetCurrentProcessId, dbgeng/IDebugSystemObjects3::GetCurrentProcessId, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentProcessId method, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentProcessId method, IDebugSystemObjects_9ae912e7-68db-45d0-8129-f55e5b3ee462.xml, IDebugSystemObjects interface [Windows Debugging], GetCurrentProcessId method, GetCurrentProcessId method [Windows Debugging], IDebugSystemObjects2, IDebugSystemObjects::GetCurrentProcessId, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentProcessId method, IDebugSystemObjects3, IDebugSystemObjects
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
-	IDebugSystemObjects.GetCurrentProcessId
-	IDebugSystemObjects2.GetCurrentProcessId
-	IDebugSystemObjects3.GetCurrentProcessId
-	IDebugSystemObjects4.GetCurrentProcessId
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetCurrentProcessId method
The <b>GetCurrentProcessId</b> method returns the engine process ID for the current process.

## Syntax

````
HRESULT GetCurrentProcessId(
  [out] PULONG Id
);
````

## Parameters

`Id`

Receives the engine process ID for the current process.


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

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |