---
UID : NF:dbgeng.IDebugControl3.RemoveEngineOptions
title : IDebugControl3::RemoveEngineOptions method
author : windows-driver-content
description : The RemoveEngineOptions method turns off some of the engine's options.
old-location : debugger\removeengineoptions.htm
old-project : debugger
ms.assetid : ec4cf252-88c4-47de-9015-bcbbd1fd5d1d
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugControl3, IDebugControl3 interface [Windows Debugging], RemoveEngineOptions method, dbgeng/IDebugControl::RemoveEngineOptions, IDebugControl_b1af0528-4fc2-4ea3-90e8-c7d92b0632f4.xml, IDebugControl2::RemoveEngineOptions, IDebugControl3::RemoveEngineOptions, RemoveEngineOptions method [Windows Debugging], IDebugControl2 interface, RemoveEngineOptions method [Windows Debugging], IDebugControl interface, IDebugControl interface [Windows Debugging], RemoveEngineOptions method, debugger.removeengineoptions, IDebugControl::RemoveEngineOptions, dbgeng/IDebugControl2::RemoveEngineOptions, IDebugControl2 interface [Windows Debugging], RemoveEngineOptions method, RemoveEngineOptions method [Windows Debugging], RemoveEngineOptions method [Windows Debugging], IDebugControl3 interface, RemoveEngineOptions, dbgeng/IDebugControl3::RemoveEngineOptions
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h, Dbgeng.h, Dbgeng.h
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


# RemoveEngineOptions method
The <b>RemoveEngineOptions</b> method turns off some of the engine's options.

## Syntax

````
HRESULT RemoveEngineOptions(
  [in] ULONG Options
);
````

## Parameters

`Options`

Specifies the engine options to turn off.  <i>Options</i> is a bit-set; the new value of the engine's options will equal the bitwise-NOT of <i>Options</i> combined with old value using the bitwise-AND operator (<code>new_value := old_value AND NOT Options</code>).  For a description of the engine options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541475">DEBUG_ENGOPT_XXX</a>.


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

After the engine options have been changed, the engine sends out notification to each client's event callback object by passing the DEBUG_CES_ENGINE_OPTIONS flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h, Dbgeng.h, Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546598">GetEngineOptions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537884">AddEngineOptions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556670">SetEngineOptions</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::RemoveEngineOptions method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>