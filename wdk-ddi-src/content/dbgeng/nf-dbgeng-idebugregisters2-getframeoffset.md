---
UID : NF:dbgeng.IDebugRegisters2.GetFrameOffset
title : IDebugRegisters2::GetFrameOffset method
author : windows-driver-content
description : The GetFrameOffset method returns the location of the stack frame for the current function.
old-location : debugger\getframeoffset.htm
old-project : debugger
ms.assetid : 09473106-3ab8-43ee-a424-2930b6bd3fcf
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugRegisters2, IDebugRegisters2::GetFrameOffset, GetFrameOffset
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
req.alt-api : IDebugRegisters.GetFrameOffset,IDebugRegisters2.GetFrameOffset
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


# GetFrameOffset method
The <b>GetFrameOffset</b> method returns the location of the stack frame for the current function.

## Syntax

````
HRESULT GetFrameOffset(
  [out] PULONG64 Offset
);
````

## Parameters

`Offset`

The location in the target's virtual address space of the stack frame for the current function.


## Return Value

This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

## Remarks

The meaning of value returned by this method is architecture-specific.

The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff546815">GetFrameOffset2</a> performs the same task as this method but also allows the register source to be specified.

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

<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546815">GetFrameOffset2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters::GetFrameOffset method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>