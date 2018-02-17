---
UID: NF:dbgeng.IDebugSystemObjects2.GetCurrentThreadSystemId
title: IDebugSystemObjects2::GetCurrentThreadSystemId method
author: windows-driver-content
description: The GetCurrentThreadSystemId method returns the system thread ID of the current thread.
old-location: debugger\getcurrentthreadsystemid.htm
old-project: debugger
ms.assetid: b2e4d14c-a97f-4f57-b0ce-5a52a82c1690
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects_67dfdace-712e-4652-96bd-d4f073c2bf0f.xml, dbgeng/IDebugSystemObjects2::GetCurrentThreadSystemId, debugger.getcurrentthreadsystemid, GetCurrentThreadSystemId method [Windows Debugging], IDebugSystemObjects interface, GetCurrentThreadSystemId method [Windows Debugging], IDebugSystemObjects2 interface, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentThreadSystemId method, GetCurrentThreadSystemId method [Windows Debugging], IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects3::GetCurrentThreadSystemId, IDebugSystemObjects::GetCurrentThreadSystemId, GetCurrentThreadSystemId method [Windows Debugging], IDebugSystemObjects2::GetCurrentThreadSystemId, IDebugSystemObjects4::GetCurrentThreadSystemId, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentThreadSystemId method, IDebugSystemObjects, IDebugSystemObjects3::GetCurrentThreadSystemId, GetCurrentThreadSystemId, IDebugSystemObjects interface [Windows Debugging], GetCurrentThreadSystemId method, dbgeng/IDebugSystemObjects::GetCurrentThreadSystemId, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentThreadSystemId method, GetCurrentThreadSystemId method [Windows Debugging], IDebugSystemObjects3 interface, dbgeng/IDebugSystemObjects4::GetCurrentThreadSystemId, IDebugSystemObjects2
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
-	IDebugSystemObjects.GetCurrentThreadSystemId
-	IDebugSystemObjects2.GetCurrentThreadSystemId
-	IDebugSystemObjects3.GetCurrentThreadSystemId
-	IDebugSystemObjects4.GetCurrentThreadSystemId
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetCurrentThreadSystemId method
The <b>GetCurrentThreadSystemId</b> method returns the system thread ID of the current thread.

## Syntax

````
HRESULT GetCurrentThreadSystemId(
  [out] PULONG SysId
);
````

## Parameters

`SysId`

Receives the system thread ID.


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

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |