---
UID : NF:dbgeng.IDebugRegisters2.GetFrameOffset2
title : IDebugRegisters2::GetFrameOffset2 method
author : windows-driver-content
description : The GetFrameOffset2 method returns the location of the stack frame for the current function.
old-location : debugger\getframeoffset2.htm
old-project : debugger
ms.assetid : e0ab18ea-4447-4eee-bdf3-d251d4d4952f
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : GetFrameOffset2 method [Windows Debugging], dbgeng/IDebugRegisters2::GetFrameOffset2, GetFrameOffset2 method [Windows Debugging], IDebugRegisters2 interface, IDebugRegisters2::GetFrameOffset2, IDebugRegisters2 interface [Windows Debugging], GetFrameOffset2 method, IDebugRegisters_9b3855a5-d5e4-4485-81f3-1584b707f73a.xml, GetFrameOffset2, debugger.getframeoffset2, IDebugRegisters2
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


# GetFrameOffset2 method
The <b>GetFrameOffset2</b> method returns the location of the stack frame for the current function.

## Syntax

````
HRESULT GetFrameOffset2(
  [in]  ULONG    Source,
  [out] PULONG64 Offset
);
````

## Parameters

`Source`

Specifies the register source to query.

The possible values are listed in the following table.
<table>
<tr>
<th>Value</th>
<th>Register source</th>
</tr>
<tr>
<td>
DEBUG_REGSRC_DEBUGGEE

</td>
<td>
Fetch register information from the target.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_EXPLICIT

</td>
<td>
Fetch register information from the current explicit <a href="https://msdn.microsoft.com/3690903c-4281-4c65-98b0-00ca22206168">register context</a>.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_FRAME

</td>
<td>
Fetch register information from the current scope's register context. 


<div class="alert"><b>Note</b>    Stack unwinding does not guarantee accurate updating of the register context, so the scope frame's register context might not be accurate in all cases.</div>
<div> </div>


</td>
</tr>
</table>

`Offset`

The location in the process's virtual address space of the stack frame for the current function.


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

The meaning of the value that is returned by this method is architecture-specific.

The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff546806">GetFrameOffset</a> performs the same task as this method but always uses the target as the register source.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546806">GetFrameOffset</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters2::GetFrameOffset2 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>