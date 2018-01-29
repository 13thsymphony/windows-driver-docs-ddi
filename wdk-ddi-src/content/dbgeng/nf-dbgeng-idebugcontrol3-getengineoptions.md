---
UID : NF:dbgeng.IDebugControl3.GetEngineOptions
title : IDebugControl3::GetEngineOptions method
author : windows-driver-content
description : The GetEngineOptions method returns the engine's options.
old-location : debugger\getengineoptions.htm
old-project : debugger
ms.assetid : a64645da-e11a-4568-9865-64eb7463892c
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugControl2 interface [Windows Debugging], GetEngineOptions method, dbgeng/IDebugControl3::GetEngineOptions, dbgeng/IDebugControl::GetEngineOptions, IDebugControl3, GetEngineOptions method [Windows Debugging], IDebugControl interface, IDebugControl::GetEngineOptions, GetEngineOptions method [Windows Debugging], IDebugControl3 interface, GetEngineOptions method [Windows Debugging], GetEngineOptions, debugger.getengineoptions, IDebugControl2::GetEngineOptions, IDebugControl3 interface [Windows Debugging], GetEngineOptions method, dbgeng/IDebugControl2::GetEngineOptions, IDebugControl_75edd4f2-c81d-408d-a61a-3c2fcf5932e6.xml, IDebugControl interface [Windows Debugging], GetEngineOptions method, GetEngineOptions method [Windows Debugging], IDebugControl2 interface, IDebugControl3::GetEngineOptions
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


# GetEngineOptions method
The <b>GetEngineOptions</b> method returns the engine's options.

## Syntax

````
HRESULT GetEngineOptions(
  [out] PULONG Options
);
````

## Parameters

`Options`

Receives a bit-set that contains the engine's options. For a description of the engine options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541475">DEBUG_ENGOPT_XXX</a>.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537884">AddEngineOptions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554491">RemoveEngineOptions</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556670">SetEngineOptions</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetEngineOptions method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>