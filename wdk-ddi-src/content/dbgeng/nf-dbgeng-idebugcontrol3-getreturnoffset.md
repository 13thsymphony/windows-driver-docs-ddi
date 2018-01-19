---
UID : NF:dbgeng.IDebugControl3.GetReturnOffset
title : IDebugControl3::GetReturnOffset method
author : windows-driver-content
description : The GetReturnOffset method returns the return address for the current function.
old-location : debugger\getreturnoffset.htm
old-project : debugger
ms.assetid : 65d72369-7ace-4d3d-a15c-6322c0066470
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugControl3, IDebugControl3::GetReturnOffset, GetReturnOffset
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDebugControl.GetReturnOffset,IDebugControl2.GetReturnOffset,IDebugControl3.GetReturnOffset
req.alt-loc : dbgeng.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

## Remarks

The return address is the location in the process's virtual address space of the instruction that will be executed when the current function returns.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |