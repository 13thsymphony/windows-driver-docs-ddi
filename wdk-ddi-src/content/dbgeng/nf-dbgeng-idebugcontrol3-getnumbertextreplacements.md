---
UID: NF:dbgeng.IDebugControl3.GetNumberTextReplacements
title: IDebugControl3::GetNumberTextReplacements method
author: windows-driver-content
description: The GetNumberTextReplacements method returns the number of currently defined user-named and automatic aliases.
old-location: debugger\getnumbertextreplacements.htm
old-project: debugger
ms.assetid: d15400a8-3d8d-48dd-86f0-4e53f8b04add
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::GetNumberTextReplacements, GetNumberTextReplacements
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
req.alt-api: IDebugControl2.GetNumberTextReplacements,IDebugControl3.GetNumberTextReplacements
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

# IDebugControl3::GetNumberTextReplacements method



## -description
The <b>GetNumberTextReplacements</b> method returns the number of currently defined user-named and automatic aliases.  



## -syntax

````
HRESULT GetNumberTextReplacements(
  [out] PULONG NumRepl
);
````


## -parameters

### -param NumRepl [out]

Receives the total number of user-named and automatic aliases.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
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
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549280">GetTextReplacement</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556818">SetTextReplacement</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553268">OutputTextReplacements</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl2::GetNumberTextReplacements method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

