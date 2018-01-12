---
UID: NF:dbgeng.IDebugControl4.GetTextMacroWide
title: IDebugControl4::GetTextMacroWide method
author: windows-driver-content
description: The GetTextMacroWide method returns the value of a fixed-name alias.
old-location: debugger\gettextmacrowide.htm
old-project: debugger
ms.assetid: 5b125041-969e-49bb-96d5-b40cc7285315
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl4, IDebugControl4::GetTextMacroWide, GetTextMacroWide
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
req.alt-api: IDebugControl4.GetTextMacroWide
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl4::GetTextMacroWide method



## -description
The <b>GetTextMacroWide</b> method returns the value of a fixed-name alias.



## -syntax

````
HRESULT GetTextMacroWide(
  [in]            ULONG  Slot,
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG MacroSize
);
````


## -parameters

### -param Slot [in]

Specifies the number of the fixed-name alias.  <i>Slot</i> can take the values 0, 1, ..., 9, that represent the fixed-name aliases <b>$u0</b>, <b>$u1</b>, ..., <b>$u9</b>.


### -param Buffer [out, optional]

Receives the value of the alias specified by <i>Slot</i>.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param MacroSize [out, optional]

Receives the size, in characters, of the value of the alias.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
Before executing commands or evaluating expressions, the debugger engine will replace the alias specified by <i>Slot</i> with the value of the alias (returned to the <i>Buffer</i> buffer).

For an overview of aliases used by the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551041">Interacting with the Engine</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556809">SetTextMacro</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549280">GetTextReplacement</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547988">GetNumberTextReplacements</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554663">r (Registers)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetTextMacroWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

