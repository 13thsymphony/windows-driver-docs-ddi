---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentProcessSystemId
title: IDebugSystemObjects4::GetCurrentProcessSystemId method
author: windows-driver-content
description: The GetCurrentProcessSystemId method returns the system process ID of the current process.
old-location: debugger\getcurrentprocesssystemid.htm
old-project: debugger
ms.assetid: 850f2f86-af0d-414a-99d7-d081753c591f
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects4 interface [Windows Debugging], GetCurrentProcessSystemId method, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentProcessSystemId method, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentProcessSystemId method, debugger.getcurrentprocesssystemid, GetCurrentProcessSystemId method [Windows Debugging], IDebugSystemObjects interface, GetCurrentProcessSystemId method [Windows Debugging], dbgeng/IDebugSystemObjects2::GetCurrentProcessSystemId, IDebugSystemObjects4, IDebugSystemObjects::GetCurrentProcessSystemId, IDebugSystemObjects3::GetCurrentProcessSystemId, GetCurrentProcessSystemId method [Windows Debugging], IDebugSystemObjects4 interface, GetCurrentProcessSystemId, IDebugSystemObjects_e2d8479b-c723-462c-b423-905186bf69e6.xml, dbgeng/IDebugSystemObjects::GetCurrentProcessSystemId, IDebugSystemObjects4::GetCurrentProcessSystemId, IDebugSystemObjects2::GetCurrentProcessSystemId, dbgeng/IDebugSystemObjects4::GetCurrentProcessSystemId, dbgeng/IDebugSystemObjects3::GetCurrentProcessSystemId, IDebugSystemObjects interface [Windows Debugging], GetCurrentProcessSystemId method, GetCurrentProcessSystemId method [Windows Debugging], IDebugSystemObjects2 interface, GetCurrentProcessSystemId method [Windows Debugging], IDebugSystemObjects3 interface
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
-	IDebugSystemObjects.GetCurrentProcessSystemId
-	IDebugSystemObjects2.GetCurrentProcessSystemId
-	IDebugSystemObjects3.GetCurrentProcessSystemId
-	IDebugSystemObjects4.GetCurrentProcessSystemId
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetCurrentProcessSystemId method
The <b>GetCurrentProcessSystemId</b> method returns the system process ID of the current process.

## Syntax

````
HRESULT GetCurrentProcessSystemId(
  [out] PULONG SysId
);
````

## Parameters

`SysId`

Receives the system process ID.


## Return Value

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The target is a kernel-mode target.

</td>
</tr>
</table>

## Remarks

This method is only available in user-mode debugging.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |