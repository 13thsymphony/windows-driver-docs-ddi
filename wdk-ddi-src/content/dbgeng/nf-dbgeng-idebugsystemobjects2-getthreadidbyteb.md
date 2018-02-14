---
UID: NF:dbgeng.IDebugSystemObjects2.GetThreadIdByTeb
title: IDebugSystemObjects2::GetThreadIdByTeb method
author: windows-driver-content
description: The GetThreadIdByTeb method returns the engine thread ID of the specified thread. The thread is specified by its thread environment block (TEB).
old-location: debugger\getthreadidbyteb.htm
old-project: debugger
ms.assetid: 64b98d8b-883b-4a2c-a5de-058bb3b732df
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects3::GetThreadIdByTeb, IDebugSystemObjects interface [Windows Debugging], GetThreadIdByTeb method, IDebugSystemObjects2::GetThreadIdByTeb, debugger.getthreadidbyteb, GetThreadIdByTeb method [Windows Debugging], IDebugSystemObjects2 interface, IDebugSystemObjects3 interface [Windows Debugging], GetThreadIdByTeb method, GetThreadIdByTeb method [Windows Debugging], dbgeng/IDebugSystemObjects3::GetThreadIdByTeb, IDebugSystemObjects_6f4062c3-c2ef-43bf-81c6-32103f37e793.xml, IDebugSystemObjects::GetThreadIdByTeb, GetThreadIdByTeb method [Windows Debugging], IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects4::GetThreadIdByTeb, GetThreadIdByTeb method [Windows Debugging], IDebugSystemObjects3 interface, dbgeng/IDebugSystemObjects::GetThreadIdByTeb, IDebugSystemObjects4 interface [Windows Debugging], GetThreadIdByTeb method, GetThreadIdByTeb, GetThreadIdByTeb method [Windows Debugging], IDebugSystemObjects interface, IDebugSystemObjects2, IDebugSystemObjects4::GetThreadIdByTeb, IDebugSystemObjects2 interface [Windows Debugging], GetThreadIdByTeb method, dbgeng/IDebugSystemObjects2::GetThreadIdByTeb, IDebugSystemObjects
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
-	IDebugSystemObjects.GetThreadIdByTeb
-	IDebugSystemObjects2.GetThreadIdByTeb
-	IDebugSystemObjects3.GetThreadIdByTeb
-	IDebugSystemObjects4.GetThreadIdByTeb
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetThreadIdByTeb method
The <b>GetThreadIdByTeb</b> method returns the engine thread ID of the specified thread.  The thread is specified by its thread environment block (TEB).

## Syntax

````
HRESULT GetThreadIdByTeb(
  [in]  ULONG64 Offset,
  [out] PULONG  Id
);
````

## Parameters

`Offset`

Specifies the location of the thread's TEB.

`Id`

Receives the engine thread ID.


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

In kernel-mode debugging, this method returns the engine thread ID for the virtual thread representing the processor on which the specified thread is executing.  If the thread is not executing on a processor, this method will fail.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |