---
UID: NF:dbgeng.IDebugControl.GetReturnOffset
title: IDebugControl::GetReturnOffset method
author: windows-driver-content
description: The GetReturnOffset method returns the return address for the current function.
old-location: debugger\getreturnoffset.htm
old-project: debugger
ms.assetid: 65d72369-7ace-4d3d-a15c-6322c0066470
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetReturnOffset method [Windows Debugging], GetReturnOffset method [Windows Debugging], IDebugControl interface, GetReturnOffset method [Windows Debugging], IDebugControl2 interface, GetReturnOffset method [Windows Debugging], IDebugControl3 interface, GetReturnOffset,IDebugControl.GetReturnOffset, IDebugControl, IDebugControl interface [Windows Debugging], GetReturnOffset method, IDebugControl2 interface [Windows Debugging], GetReturnOffset method, IDebugControl2::GetReturnOffset, IDebugControl3 interface [Windows Debugging], GetReturnOffset method, IDebugControl3::GetReturnOffset, IDebugControl::GetReturnOffset, IDebugControl_7c101d44-aa43-48d4-8176-2ed110eca231.xml, dbgeng/IDebugControl2::GetReturnOffset, dbgeng/IDebugControl3::GetReturnOffset, dbgeng/IDebugControl::GetReturnOffset, debugger.getreturnoffset
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
-	IDebugControl.GetReturnOffset
-	IDebugControl2.GetReturnOffset
-	IDebugControl3.GetReturnOffset
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugControl::GetReturnOffset method
The <b>GetReturnOffset</b> method returns the return address for the current function.

## Syntax

```
HRESULT GetReturnOffset(
  PULONG64 Offset
);
```

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