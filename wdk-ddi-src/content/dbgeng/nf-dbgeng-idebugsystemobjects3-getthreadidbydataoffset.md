---
UID: NF:dbgeng.IDebugSystemObjects3.GetThreadIdByDataOffset
title: IDebugSystemObjects3::GetThreadIdByDataOffset method
author: windows-driver-content
description: The GetThreadIdByDataOffset method returns the engine thread ID for the specified thread. The thread is specified by its system data structure.
old-location: debugger\getthreadidbydataoffset.htm
old-project: debugger
ms.assetid: f559e0da-ca5c-4fea-aa17-257abfd45f96
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects_bb1b0f35-219b-4883-8df7-d90a96441720.xml, IDebugSystemObjects2::GetThreadIdByDataOffset, dbgeng/IDebugSystemObjects4::GetThreadIdByDataOffset, dbgeng/IDebugSystemObjects2::GetThreadIdByDataOffset, IDebugSystemObjects2 interface [Windows Debugging], GetThreadIdByDataOffset method, debugger.getthreadidbydataoffset, IDebugSystemObjects::GetThreadIdByDataOffset, dbgeng/IDebugSystemObjects::GetThreadIdByDataOffset, GetThreadIdByDataOffset method [Windows Debugging], IDebugSystemObjects4 interface, GetThreadIdByDataOffset method [Windows Debugging], IDebugSystemObjects interface [Windows Debugging], GetThreadIdByDataOffset method, GetThreadIdByDataOffset, IDebugSystemObjects, IDebugSystemObjects3 interface [Windows Debugging], GetThreadIdByDataOffset method, IDebugSystemObjects3::GetThreadIdByDataOffset, IDebugSystemObjects4 interface [Windows Debugging], GetThreadIdByDataOffset method, dbgeng/IDebugSystemObjects3::GetThreadIdByDataOffset, GetThreadIdByDataOffset method [Windows Debugging], IDebugSystemObjects interface, GetThreadIdByDataOffset method [Windows Debugging], IDebugSystemObjects2 interface, IDebugSystemObjects4::GetThreadIdByDataOffset, GetThreadIdByDataOffset method [Windows Debugging], IDebugSystemObjects3 interface, IDebugSystemObjects2, IDebugSystemObjects3
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
-	IDebugSystemObjects.GetThreadIdByDataOffset
-	IDebugSystemObjects2.GetThreadIdByDataOffset
-	IDebugSystemObjects3.GetThreadIdByDataOffset
-	IDebugSystemObjects4.GetThreadIdByDataOffset
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetThreadIdByDataOffset method
The <b>GetThreadIdByDataOffset</b> method returns the engine thread ID for the specified thread.  The thread is specified by its system data structure.

## Syntax

````
HRESULT GetThreadIdByDataOffset(
  [in]  ULONG64 Offset,
  [out] PULONG  Id
);
````

## Parameters

`Offset`

Specifies the location of the system data structure for the thread.

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