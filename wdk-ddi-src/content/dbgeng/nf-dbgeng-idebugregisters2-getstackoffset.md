---
UID : NF:dbgeng.IDebugRegisters2.GetStackOffset
title : IDebugRegisters2::GetStackOffset method
author : windows-driver-content
description : The GetStackOffset method returns the current thread's current stack location.
old-location : debugger\getstackoffset.htm
old-project : debugger
ms.assetid : 7368a2d6-fea3-411e-85d9-c09764bb3b8e
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugRegisters::GetStackOffset, GetStackOffset method [Windows Debugging], IDebugRegisters interface, IDebugRegisters_40c9da48-e41f-4890-ace2-b15a2e1cc4ba.xml, GetStackOffset method [Windows Debugging], GetStackOffset, dbgeng/IDebugRegisters::GetStackOffset, IDebugRegisters interface [Windows Debugging], GetStackOffset method, IDebugRegisters2::GetStackOffset, IDebugRegisters2 interface [Windows Debugging], GetStackOffset method, dbgeng/IDebugRegisters2::GetStackOffset, GetStackOffset method [Windows Debugging], IDebugRegisters2 interface, debugger.getstackoffset, IDebugRegisters2
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


# GetStackOffset method
The <b>GetStackOffset</b> method returns the current thread's current stack location.

## Syntax

````
HRESULT GetStackOffset(
  [out] PULONG64 Offset
);
````

## Parameters

`Offset`

Receives the location in the process's virtual address space of the current thread's current stack location.


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

The meaning of value returned by this method is architecture specific.

The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff548414">GetStackOffset2</a> performs the same task as this method but also allows the register source to be specified.

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

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548414">GetStackOffset2</a>

<a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters::GetStackOffset method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>