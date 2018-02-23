---
UID: NF:dbgeng.IDebugControl3.GetReturnOffset
title: IDebugControl3::GetReturnOffset method
author: windows-driver-content
description: The GetReturnOffset method returns the return address for the current function.
old-location: debugger\getreturnoffset.htm
old-project: Debugger
ms.assetid: 65d72369-7ace-4d3d-a15c-6322c0066470
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GetReturnOffset method [Windows Debugging], IDebugControl interface, debugger.getreturnoffset, dbgeng/IDebugControl3::GetReturnOffset, IDebugControl2::GetReturnOffset, IDebugControl_7c101d44-aa43-48d4-8176-2ed110eca231.xml, IDebugControl3::GetReturnOffset, IDebugControl3 interface [Windows Debugging], GetReturnOffset method, IDebugControl, GetReturnOffset method [Windows Debugging], IDebugControl3 interface, IDebugControl2, GetReturnOffset, GetReturnOffset method [Windows Debugging], IDebugControl interface [Windows Debugging], GetReturnOffset method, dbgeng/IDebugControl2::GetReturnOffset, IDebugControl::GetReturnOffset, dbgeng/IDebugControl::GetReturnOffset, IDebugControl3, IDebugControl2 interface [Windows Debugging], GetReturnOffset method, GetReturnOffset method [Windows Debugging], IDebugControl2 interface
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
-	IDebugControl.GetReturnOffset
-	IDebugControl2.GetReturnOffset
-	IDebugControl3.GetReturnOffset
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetReturnOffset method
The <b>GetReturnOffset</b> method returns the return address for the current function.

## Syntax

````
HRESULT GetReturnOffset(
  [out] PULONG64 Offset
);
````

## Parameters

`Offset`

Receives the return address.


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

The return address is the location in the process's virtual address space of the instruction that will be executed when the current function returns.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |