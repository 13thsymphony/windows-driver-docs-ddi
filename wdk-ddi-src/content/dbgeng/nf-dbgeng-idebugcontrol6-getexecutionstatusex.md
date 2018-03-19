---
UID: NF:dbgeng.IDebugControl6.GetExecutionStatusEx
title: IDebugControl6::GetExecutionStatusEx method
author: windows-driver-content
description: The GetExecutionStatusEx method returns information about the execution status of the debugger engine.
old-location: debugger\idebugcontrol6_getexecutionstatusex.htm
old-project: debugger
ms.assetid: C14A3106-AEF7-4BA2-9E21-32D8B2D5BD7E
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetExecutionStatusEx method [Windows Debugging], GetExecutionStatusEx method [Windows Debugging], IDebugControl6 interface, GetExecutionStatusEx,IDebugControl6.GetExecutionStatusEx, IDebugControl6, IDebugControl6 interface [Windows Debugging], GetExecutionStatusEx method, IDebugControl6::GetExecutionStatusEx, dbgeng/IDebugControl6::GetExecutionStatusEx, debugger.idebugcontrol6_getexecutionstatusex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: 
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
req.lib: 
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
-	IDebugControl6.GetExecutionStatusEx
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetExecutionStatusEx method
The GetExecutionStatusEx method returns information about the execution status of the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.

## Syntax

````
HRESULT GetExecutionStatusEx(
  [out] PULONG Status
);
````

## Parameters

`Status`

Receives the extended execution status.  This will be set to values described in  <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a>.


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

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol6.md">IDebugControl6</a>