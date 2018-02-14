---
UID: NF:dbgeng.IDebugControl.IsPointer64Bit
title: IDebugControl::IsPointer64Bit method
author: windows-driver-content
description: The IsPointer64Bit method determines if the effective processor uses 64-bit pointers.
old-location: debugger\ispointer64bit.htm
old-project: debugger
ms.assetid: 01003268-844e-4613-ac13-0306396e56b9
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl_62a0cc8d-e542-4889-9f68-591d00828d4b.xml, IDebugControl3::IsPointer64Bit, IsPointer64Bit method [Windows Debugging], IDebugControl2 interface, IsPointer64Bit method [Windows Debugging], IDebugControl3 interface, IDebugControl2::IsPointer64Bit, IsPointer64Bit, dbgeng/IDebugControl3::IsPointer64Bit, IDebugControl::IsPointer64Bit, IDebugControl, IDebugControl interface [Windows Debugging], IsPointer64Bit method, debugger.ispointer64bit, IDebugControl3 interface [Windows Debugging], IsPointer64Bit method, IsPointer64Bit method [Windows Debugging], IDebugControl interface, dbgeng/IDebugControl::IsPointer64Bit, IDebugControl2 interface [Windows Debugging], IsPointer64Bit method, dbgeng/IDebugControl2::IsPointer64Bit, IsPointer64Bit method [Windows Debugging]
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
-	IDebugControl.IsPointer64Bit
-	IDebugControl2.IsPointer64Bit
-	IDebugControl3.IsPointer64Bit
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# IsPointer64Bit method
The <b>IsPointer64Bit</b> method determines if the effective processor uses 64-bit pointers.

## Syntax

````
HRESULT IsPointer64Bit();
````

## Parameters

This function has no parameters.

## Return Value

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
The effective processor uses 64-bit pointers.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The effective processor does not use 64-bit pointers.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h |
| **Library** | dbgeng.h |