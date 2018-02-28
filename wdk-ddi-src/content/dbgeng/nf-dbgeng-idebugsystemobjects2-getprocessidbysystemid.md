---
UID: NF:dbgeng.IDebugSystemObjects2.GetProcessIdBySystemId
title: IDebugSystemObjects2::GetProcessIdBySystemId method
author: windows-driver-content
description: The GetProcessIdBySystemId method returns the engine process ID for a process specified by its system process ID.
old-location: debugger\getprocessidbysystemid.htm
old-project: debugger
ms.assetid: 7260f0ea-5e8b-4b08-8c8f-70216ffe54a9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetProcessIdBySystemId method [Windows Debugging], GetProcessIdBySystemId method [Windows Debugging], IDebugSystemObjects interface, GetProcessIdBySystemId method [Windows Debugging], IDebugSystemObjects2 interface, GetProcessIdBySystemId method [Windows Debugging], IDebugSystemObjects3 interface, GetProcessIdBySystemId method [Windows Debugging], IDebugSystemObjects4 interface, GetProcessIdBySystemId,IDebugSystemObjects2.GetProcessIdBySystemId, IDebugSystemObjects interface [Windows Debugging], GetProcessIdBySystemId method, IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], GetProcessIdBySystemId method, IDebugSystemObjects2::GetProcessIdBySystemId, IDebugSystemObjects3 interface [Windows Debugging], GetProcessIdBySystemId method, IDebugSystemObjects3::GetProcessIdBySystemId, IDebugSystemObjects4 interface [Windows Debugging], GetProcessIdBySystemId method, IDebugSystemObjects4::GetProcessIdBySystemId, IDebugSystemObjects::GetProcessIdBySystemId, IDebugSystemObjects_45c888bc-6771-4cd4-843e-aeafd8c6c6cb.xml, dbgeng/IDebugSystemObjects2::GetProcessIdBySystemId, dbgeng/IDebugSystemObjects3::GetProcessIdBySystemId, dbgeng/IDebugSystemObjects4::GetProcessIdBySystemId, dbgeng/IDebugSystemObjects::GetProcessIdBySystemId, debugger.getprocessidbysystemid
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSystemObjects.GetProcessIdBySystemId
-	IDebugSystemObjects2.GetProcessIdBySystemId
-	IDebugSystemObjects3.GetProcessIdBySystemId
-	IDebugSystemObjects4.GetProcessIdBySystemId
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetProcessIdBySystemId method
The <b>GetProcessIdBySystemId</b> method returns the engine process ID for a process specified by its system process ID.

## Syntax

````
HRESULT GetProcessIdBySystemId(
  [in]  ULONG  SysId,
  [out] PULONG Id
);
````

## Parameters

`SysId`

Specifies the system process ID.

`Id`

Receives the engine process ID.


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