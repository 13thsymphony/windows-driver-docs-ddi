---
UID: NF:dbgeng.IDebugDataSpaces3.WriteMsr
title: IDebugDataSpaces3::WriteMsr method
author: windows-driver-content
description: The WriteMsr method writes a value to the specified Model-Specific Register (MSR).
old-location: debugger\writemsr2.htm
old-project: debugger
ms.assetid: c9838b9e-b390-455d-98d6-249a49c9165d
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugDataSpaces3 interface [Windows Debugging], WriteMsr method, IDebugDataSpaces3::WriteMsr, IDebugDataSpaces2::WriteMsr, dbgeng/IDebugDataSpaces2::WriteMsr, dbgeng/IDebugDataSpaces::WriteMsr, IDebugDataSpaces::WriteMsr, WriteMsr, IDebugDataSpaces4::WriteMsr, IDebugDataSpaces, IDebugDataSpaces4 interface [Windows Debugging], WriteMsr method, dbgeng/IDebugDataSpaces3::WriteMsr, IDebugDataSpaces interface [Windows Debugging], WriteMsr method, WriteMsr method [Windows Debugging], dbgeng/IDebugDataSpaces4::WriteMsr, IDebugDataSpaces2 interface [Windows Debugging], WriteMsr method, WriteMsr method [Windows Debugging], IDebugDataSpaces interface, IDebugDataSpaces3, WriteMsr method [Windows Debugging], IDebugDataSpaces4 interface, IDebugDataSpaces_b0b0220e-66d2-4d96-b4bf-3016b0ed677c.xml, debugger.writemsr2, WriteMsr method [Windows Debugging], IDebugDataSpaces2 interface, IDebugDataSpaces2, WriteMsr method [Windows Debugging], IDebugDataSpaces3 interface
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
-	Dbgeng.h
apiname:
-	IDebugDataSpaces.WriteMsr
-	IDebugDataSpaces2.WriteMsr
-	IDebugDataSpaces3.WriteMsr
-	IDebugDataSpaces4.WriteMsr
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# WriteMsr method
The <b>WriteMsr</b> method writes a value to the specified Model-Specific Register (MSR).

## Syntax

````
HRESULT WriteMsr(
   ULONG   Msr,
   ULONG64 Value
);
````

## Parameters

`Msr`

Specifies the MSR address.

`Value`

Specifies the value to write to the MSR.


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
The method was successful.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

This method is only available in kernel-mode debugging.

For details on the addresses and values of MSRs, see the processor documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |