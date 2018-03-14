---
UID: NF:dbgeng.IDebugSystemObjects4.GetImplicitProcessDataOffset
title: IDebugSystemObjects4::GetImplicitProcessDataOffset method
author: windows-driver-content
description: The GetImplicitProcessDataOffset method returns the implicit process for the current target.
old-location: debugger\getimplicitprocessdataoffset.htm
old-project: debugger
ms.assetid: 20a11f3b-cc49-4080-ac4c-b8e18d4b2f73
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetImplicitProcessDataOffset method [Windows Debugging], GetImplicitProcessDataOffset method [Windows Debugging], IDebugSystemObjects2 interface, GetImplicitProcessDataOffset method [Windows Debugging], IDebugSystemObjects3 interface, GetImplicitProcessDataOffset method [Windows Debugging], IDebugSystemObjects4 interface, GetImplicitProcessDataOffset,IDebugSystemObjects4.GetImplicitProcessDataOffset, IDebugSystemObjects2 interface [Windows Debugging], GetImplicitProcessDataOffset method, IDebugSystemObjects2::GetImplicitProcessDataOffset, IDebugSystemObjects3 interface [Windows Debugging], GetImplicitProcessDataOffset method, IDebugSystemObjects3::GetImplicitProcessDataOffset, IDebugSystemObjects4, IDebugSystemObjects4 interface [Windows Debugging], GetImplicitProcessDataOffset method, IDebugSystemObjects4::GetImplicitProcessDataOffset, IDebugSystemObjects_3ec83d96-a7ff-4767-be21-b822c45ae01e.xml, dbgeng/IDebugSystemObjects2::GetImplicitProcessDataOffset, dbgeng/IDebugSystemObjects3::GetImplicitProcessDataOffset, dbgeng/IDebugSystemObjects4::GetImplicitProcessDataOffset, debugger.getimplicitprocessdataoffset
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
-	IDebugSystemObjects2.GetImplicitProcessDataOffset
-	IDebugSystemObjects3.GetImplicitProcessDataOffset
-	IDebugSystemObjects4.GetImplicitProcessDataOffset
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetImplicitProcessDataOffset method
The <b>GetImplicitProcessDataOffset</b> method returns the implicit process for the current target.

## Syntax

````
HRESULT GetImplicitProcessDataOffset(
  [out] PULONG64 Offset
);
````

## Parameters

`Offset`

Receives the location in the target's memory address space of the data structure of the system process that is the implicit process for the current target.


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

In kernel-mode debugging, the data structure is the KPROCESS structure for the process.

In user-mode debugging, the data structure is the process environment block (PEB) for the process.

For more information about the implicit process, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the KPROCESS and PEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |