---
UID : NF:dbgeng.IDebugRegisters2.GetNumberRegisters
title : IDebugRegisters2::GetNumberRegisters method
author : windows-driver-content
description : The GetNumberRegisters method returns the number of registers on the target computer.
old-location : debugger\getnumberregisters.htm
old-project : debugger
ms.assetid : 51c521fc-e89c-49c9-8110-de31af3bed83
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugRegisters::GetNumberRegisters, dbgeng/IDebugRegisters::GetNumberRegisters, GetNumberRegisters method [Windows Debugging], GetNumberRegisters method [Windows Debugging], IDebugRegisters interface, IDebugRegisters2 interface [Windows Debugging], GetNumberRegisters method, GetNumberRegisters method [Windows Debugging], IDebugRegisters2 interface, IDebugRegisters_b2fa1d95-0331-4c27-a3af-3cc8e895e88f.xml, GetNumberRegisters, dbgeng/IDebugRegisters2::GetNumberRegisters, IDebugRegisters interface [Windows Debugging], GetNumberRegisters method, IDebugRegisters2::GetNumberRegisters, debugger.getnumberregisters, IDebugRegisters2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : DbgEng.h
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
req.typenames : DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetNumberRegisters method
The <b>GetNumberRegisters</b> method returns the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">registers</a> on the target computer.

## Syntax

````
HRESULT GetNumberRegisters(
  [out] PULONG Number
);
````

## Parameters

`Number`

Receives the number of registers on the target's computer.


## Return Value

This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.
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

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include DbgEng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |