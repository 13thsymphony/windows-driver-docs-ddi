---
UID : NF:dbgeng.IDebugSystemObjects4.GetProcessIdByPeb
title : IDebugSystemObjects4::GetProcessIdByPeb method
author : windows-driver-content
description : The GetProcessIdByPeb method returns the engine process ID for the specified process. The process is specified by its process environment block (PEB).
old-location : debugger\getprocessidbypeb.htm
old-project : debugger
ms.assetid : 2ee2b610-30c7-4932-b8f6-df5040a5bad8
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : dbgeng/IDebugSystemObjects::GetProcessIdByPeb, IDebugSystemObjects4::GetProcessIdByPeb, GetProcessIdByPeb method [Windows Debugging], IDebugSystemObjects2 interface, IDebugSystemObjects2::GetProcessIdByPeb, dbgeng/IDebugSystemObjects2::GetProcessIdByPeb, dbgeng/IDebugSystemObjects4::GetProcessIdByPeb, GetProcessIdByPeb method [Windows Debugging], IDebugSystemObjects3 interface, GetProcessIdByPeb method [Windows Debugging], IDebugSystemObjects4 interface, IDebugSystemObjects4 interface [Windows Debugging], GetProcessIdByPeb method, IDebugSystemObjects3::GetProcessIdByPeb, IDebugSystemObjects_f5f2396d-d537-40a0-987d-314a9dfb01ff.xml, IDebugSystemObjects interface [Windows Debugging], GetProcessIdByPeb method, IDebugSystemObjects3 interface [Windows Debugging], GetProcessIdByPeb method, IDebugSystemObjects4, debugger.getprocessidbypeb, GetProcessIdByPeb method [Windows Debugging], GetProcessIdByPeb, IDebugSystemObjects2 interface [Windows Debugging], GetProcessIdByPeb method, dbgeng/IDebugSystemObjects3::GetProcessIdByPeb, IDebugSystemObjects::GetProcessIdByPeb, GetProcessIdByPeb method [Windows Debugging], IDebugSystemObjects interface
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


# GetProcessIdByPeb method
The <b>GetProcessIdByPeb</b> method returns the engine process ID for the specified process.  The process is specified by its process environment block (PEB).

## Syntax

````
HRESULT GetProcessIdByPeb(
  [in]  ULONG64 Offset,
  [out] PULONG  Id
);
````

## Parameters

`Offset`

Specifies the location in the target's virtual address space of the PEB of the process whose process ID is requested.

`Id`

Receives the engine process ID.


## Return Value

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
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
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The target is a kernel-mode target.  This method is currently not available in kernel-mode debugging.

</td>
</tr>
</table>

## Remarks

This method is not available in kernel-mode debugging.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

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