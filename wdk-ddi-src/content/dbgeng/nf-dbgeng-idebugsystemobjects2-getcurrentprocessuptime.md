---
UID: NF:dbgeng.IDebugSystemObjects2.GetCurrentProcessUpTime
title: IDebugSystemObjects2::GetCurrentProcessUpTime method
author: windows-driver-content
description: The GetCurrentProcessUpTime method returns the length of time the current process has been running.
old-location: debugger\getcurrentprocessuptime.htm
old-project: debugger
ms.assetid: 6c6f3824-5e04-45df-8128-f3778aaa3636
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugSystemObjects2::GetCurrentProcessUpTime, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentProcessUpTime method, GetCurrentProcessUpTime method [Windows Debugging], IDebugSystemObjects2 interface, GetCurrentProcessUpTime method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentProcessUpTime method [Windows Debugging], IDebugSystemObjects4 interface, debugger.getcurrentprocessuptime, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentProcessUpTime method, IDebugSystemObjects4::GetCurrentProcessUpTime, IDebugSystemObjects_cf0611a9-8535-4e53-ae13-32d46b887954.xml, IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentProcessUpTime method, GetCurrentProcessUpTime, dbgeng/IDebugSystemObjects4::GetCurrentProcessUpTime, IDebugSystemObjects3::GetCurrentProcessUpTime, dbgeng/IDebugSystemObjects3::GetCurrentProcessUpTime, IDebugSystemObjects2::GetCurrentProcessUpTime, GetCurrentProcessUpTime method [Windows Debugging]
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
-	IDebugSystemObjects2.GetCurrentProcessUpTime
-	IDebugSystemObjects3.GetCurrentProcessUpTime
-	IDebugSystemObjects4.GetCurrentProcessUpTime
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetCurrentProcessUpTime method
The <b>GetCurrentProcessUpTime</b> method returns the length of time the current process has been running.

## Syntax

````
HRESULT GetCurrentProcessUpTime(
  [out] PULONG UpTime
);
````

## Parameters

`UpTime`

Receives the number of seconds the current process has been running.


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


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |