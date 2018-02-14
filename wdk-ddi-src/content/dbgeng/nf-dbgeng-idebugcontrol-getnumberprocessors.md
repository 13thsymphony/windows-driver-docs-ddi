---
UID: NF:dbgeng.IDebugControl.GetNumberProcessors
title: IDebugControl::GetNumberProcessors method
author: windows-driver-content
description: The GetNumberProcessors method returns the number of processors on the computer running the current target.
old-location: debugger\getnumberprocessors.htm
old-project: debugger
ms.assetid: b3f4af4e-dbba-4f14-8935-f894865cbe7d
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugControl2::GetNumberProcessors, IDebugControl2 interface [Windows Debugging], GetNumberProcessors method, IDebugControl::GetNumberProcessors, dbgeng/IDebugControl3::GetNumberProcessors, GetNumberProcessors method [Windows Debugging], IDebugControl3 interface, GetNumberProcessors method [Windows Debugging], IDebugControl2 interface, GetNumberProcessors method [Windows Debugging], IDebugControl interface [Windows Debugging], GetNumberProcessors method, IDebugControl_0ddf74be-971f-4bd8-bdfd-4ceedfbbdc0f.xml, IDebugControl, IDebugControl3 interface [Windows Debugging], GetNumberProcessors method, IDebugControl3::GetNumberProcessors, dbgeng/IDebugControl::GetNumberProcessors, GetNumberProcessors, debugger.getnumberprocessors, GetNumberProcessors method [Windows Debugging], IDebugControl interface, IDebugControl2::GetNumberProcessors
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
-	IDebugControl.GetNumberProcessors
-	IDebugControl2.GetNumberProcessors
-	IDebugControl3.GetNumberProcessors
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetNumberProcessors method
The <b>GetNumberProcessors</b> method returns the number of processors on the computer running the current target.

## Syntax

````
HRESULT GetNumberProcessors(
  [out] PULONG Number
);
````

## Parameters

`Number`

Receives the number of processors.


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
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |