---
UID : NF:dbgeng.IDebugRegisters2.GetIndexByNameWide
title : IDebugRegisters2::GetIndexByNameWide method
author : windows-driver-content
description : The GetIndexByNameWide method returns the index of the named register.
old-location : debugger\getindexbynamewide.htm
old-project : debugger
ms.assetid : eb6a50b4-275f-42c9-8121-17677971ebb2
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugRegisters2::GetIndexByNameWide, dbgeng/IDebugRegisters2::GetIndexByNameWide, IDebugRegisters2 interface [Windows Debugging], GetIndexByNameWide method, debugger.getindexbynamewide, IDebugRegisters2, GetIndexByNameWide method [Windows Debugging], IDebugRegisters2 interface, GetIndexByNameWide method [Windows Debugging], GetIndexByNameWide
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


# GetIndexByNameWide method
The <b>GetIndexByNameWide</b> method returns the index of the named register.

## Syntax

````
HRESULT GetIndexByNameWide(
  [in]  PCWSTR Name,
  [out] PULONG Index
);
````

## Parameters

`Name`

Specifies the name of the register whose index is requested.

`Index`

Receives the index of the register.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The register was not found.

</td>
</tr>
</table>

## Remarks

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include DbgEng.h) |
| **Library** | dbgeng.h |