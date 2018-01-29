---
UID : NF:dbgeng.IDebugControl3.GetNearInstruction
title : IDebugControl3::GetNearInstruction method
author : windows-driver-content
description : The GetNearInstruction method returns the location of a processor instruction relative to a given location.
old-location : debugger\getnearinstruction.htm
old-project : debugger
ms.assetid : 76387681-cac6-4c35-9095-28942a856c30
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : dbgeng/IDebugControl2::GetNearInstruction, GetNearInstruction, debugger.getnearinstruction, IDebugControl3::GetNearInstruction, GetNearInstruction method [Windows Debugging], dbgeng/IDebugControl::GetNearInstruction, IDebugControl::GetNearInstruction, IDebugControl_2c12e1fe-0f9b-45d6-9ff4-477bc42b2275.xml, GetNearInstruction method [Windows Debugging], IDebugControl interface, IDebugControl2 interface [Windows Debugging], GetNearInstruction method, IDebugControl2::GetNearInstruction, GetNearInstruction method [Windows Debugging], IDebugControl3 interface, dbgeng/IDebugControl3::GetNearInstruction, GetNearInstruction method [Windows Debugging], IDebugControl2 interface, IDebugControl3, IDebugControl interface [Windows Debugging], GetNearInstruction method, IDebugControl3 interface [Windows Debugging], GetNearInstruction method
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : dbgeng.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetNearInstruction method
The <b>GetNearInstruction</b> method returns the location of a processor instruction relative to a given location.

## Syntax

````
HRESULT GetNearInstruction(
  [in]  ULONG64  Offset,
  [in]  LONG     Delta,
  [out] PULONG64 NearOffset
);
````

## Parameters

`Offset`

Specifies the location in the process's virtual address space from which to start looking for the desired instruction.

`Delta`

Specifies the number of instructions from <i>Offset</i> of the desired instruction.  If <i>Delta</i> is negative, the returned offset is before <i>Offset</i> (see the Remarks section for more information).

`NearOffset`

Receives the location in the process's virtual address space of the instruction that is <i>Delta</i> instructions away from <i>Offset</i>.


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

On some architectures, like x86 and x64, the size of an instruction may vary.  On these architectures, when <i>Delta</i> is negative, the desired instruction location might not be uniquely defined.  In this case, the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> will search backward from <i>Offset</i> until it encounters a location such that there are the <i>Delta</i> number of instructions between that location and <i>Offset</i>.

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