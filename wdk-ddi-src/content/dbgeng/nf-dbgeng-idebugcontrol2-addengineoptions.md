---
UID: NF:dbgeng.IDebugControl2.AddEngineOptions
title: IDebugControl2::AddEngineOptions method
author: windows-driver-content
description: The AddEngineOptions method turns on some of the debugger engine's options.
old-location: debugger\addengineoptions.htm
old-project: debugger
ms.assetid: 088036f5-13cb-47ba-953c-a71c923f028e
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl2, dbgeng/IDebugControl3::AddEngineOptions, IDebugControl interface [Windows Debugging], AddEngineOptions method, IDebugControl3::AddEngineOptions, dbgeng/IDebugControl2::AddEngineOptions, IDebugControl_6042b0b9-8175-4790-be19-43f8659716dc.xml, dbgeng/IDebugControl::AddEngineOptions, AddEngineOptions method [Windows Debugging], IDebugControl, AddEngineOptions method [Windows Debugging], IDebugControl3 interface, AddEngineOptions method [Windows Debugging], IDebugControl2 interface, AddEngineOptions, IDebugControl3 interface [Windows Debugging], AddEngineOptions method, IDebugControl::AddEngineOptions, IDebugControl2 interface [Windows Debugging], AddEngineOptions method, debugger.addengineoptions, IDebugControl2::AddEngineOptions, AddEngineOptions method [Windows Debugging], IDebugControl interface
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Dbgeng.h
apiname:
-	IDebugControl.AddEngineOptions
-	IDebugControl2.AddEngineOptions
-	IDebugControl3.AddEngineOptions
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# AddEngineOptions method
The <b>AddEngineOptions</b> method turns on some of the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>'s options.

## Syntax

````
HRESULT AddEngineOptions(
  [in] ULONG Options
);
````

## Parameters

`Options`

Specifies engine options to turn on.  <i>Options</i> is a bit-set that will be combined with the existing engine options using the bitwise-OR operator.  For a description of the engine options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541475">DEBUG_ENGOPT_XXX</a>.


## Return Value

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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

After the engine options have been changed, the engine sends out notification to each client's <a href="https://msdn.microsoft.com/1e32bd40-8c77-4c6b-913c-6ec26707ed36">event callback object</a> by passing the DEBUG_CES_ENGINE_OPTIONS flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554491">RemoveEngineOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556670">SetEngineOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546598">GetEngineOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::AddEngineOptions method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>