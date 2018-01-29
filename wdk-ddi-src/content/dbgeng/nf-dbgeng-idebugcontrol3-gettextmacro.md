---
UID : NF:dbgeng.IDebugControl3.GetTextMacro
title : IDebugControl3::GetTextMacro method
author : windows-driver-content
description : The GetTextMacro method returns the value of a fixed-name alias.
old-location : debugger\gettextmacro.htm
old-project : debugger
ms.assetid : 980bcf7b-8e4a-4516-ab71-af60a1d8e99c
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugControl interface [Windows Debugging], GetTextMacro method, dbgeng/IDebugControl::GetTextMacro, IDebugControl2 interface [Windows Debugging], GetTextMacro method, GetTextMacro method [Windows Debugging], IDebugControl3 interface, IDebugControl3, GetTextMacro method [Windows Debugging], debugger.gettextmacro, GetTextMacro method [Windows Debugging], IDebugControl2 interface, IDebugControl_b6408c67-fb45-4a11-94b4-24099f406a8a.xml, IDebugControl::GetTextMacro, IDebugControl3 interface [Windows Debugging], GetTextMacro method, IDebugControl2::GetTextMacro, dbgeng/IDebugControl3::GetTextMacro, GetTextMacro method [Windows Debugging], IDebugControl interface, IDebugControl3::GetTextMacro, GetTextMacro, dbgeng/IDebugControl2::GetTextMacro
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


# GetTextMacro method
The <b>GetTextMacro</b> method returns the value of a fixed-name alias.

## Syntax

````
HRESULT GetTextMacro(
  [in]            ULONG  Slot,
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG MacroSize
);
````

## Parameters

`Slot`

Specifies the number of the fixed-name alias.  <i>Slot</i> can take the values 0, 1, ..., 9, that represent the fixed-name aliases <b>$u0</b>, <b>$u1</b>, ..., <b>$u9</b>.

`Buffer`

Receives the value of the alias specified by <i>Slot</i>.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

`BufferSize`

Specifies the size, in characters, of the <i>Buffer</i> buffer.

`MacroSize`

Receives the size, in characters, of the value of the alias.


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

Before executing commands or evaluating expressions, the debugger engine will replace the alias specified by <i>Slot</i> with the value of the alias (returned to the <i>Buffer</i> buffer).

For an overview of aliases used by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551041">Interacting with the Engine</a>.

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

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547988">GetNumberTextReplacements</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549280">GetTextReplacement</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554663">r (Registers)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556809">SetTextMacro</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetTextMacro method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>