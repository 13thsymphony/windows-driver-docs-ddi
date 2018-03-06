---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentThreadHandle
title: IDebugSystemObjects4::GetCurrentThreadHandle method
author: windows-driver-content
description: The GetCurrentThreadHandle method returns the system handle for the current thread.
old-location: debugger\getcurrentthreadhandle.htm
old-project: debugger
ms.assetid: edbda821-8016-48db-a2f5-7f615428da0c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetCurrentThreadHandle method [Windows Debugging], GetCurrentThreadHandle method [Windows Debugging], IDebugSystemObjects interface, GetCurrentThreadHandle method [Windows Debugging], IDebugSystemObjects2 interface, GetCurrentThreadHandle method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentThreadHandle method [Windows Debugging], IDebugSystemObjects4 interface, GetCurrentThreadHandle,IDebugSystemObjects4.GetCurrentThreadHandle, IDebugSystemObjects interface [Windows Debugging], GetCurrentThreadHandle method, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentThreadHandle method, IDebugSystemObjects2::GetCurrentThreadHandle, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentThreadHandle method, IDebugSystemObjects3::GetCurrentThreadHandle, IDebugSystemObjects4, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentThreadHandle method, IDebugSystemObjects4::GetCurrentThreadHandle, IDebugSystemObjects::GetCurrentThreadHandle, IDebugSystemObjects_6c615962-bf20-4cdb-8bab-8afc142e8c65.xml, dbgeng/IDebugSystemObjects2::GetCurrentThreadHandle, dbgeng/IDebugSystemObjects3::GetCurrentThreadHandle, dbgeng/IDebugSystemObjects4::GetCurrentThreadHandle, dbgeng/IDebugSystemObjects::GetCurrentThreadHandle, debugger.getcurrentthreadhandle
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
-	IDebugSystemObjects.GetCurrentThreadHandle
-	IDebugSystemObjects2.GetCurrentThreadHandle
-	IDebugSystemObjects3.GetCurrentThreadHandle
-	IDebugSystemObjects4.GetCurrentThreadHandle
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetCurrentThreadHandle method
The <b>GetCurrentThreadHandle</b> method returns the system handle for the current thread.

## Syntax

````
HRESULT GetCurrentThreadHandle(
  [out] PULONG64 Handle
);
````

## Parameters

`Handle`

Receives the current thread's system handle.


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
</table>

## Remarks

In kernel-mode debugging, an artificial handle is created because the threads are virtual threads.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on system handles, see <a href="https://msdn.microsoft.com/3be5c842-d1b6-4c34-8990-e23e2d08dd23">Handles</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |