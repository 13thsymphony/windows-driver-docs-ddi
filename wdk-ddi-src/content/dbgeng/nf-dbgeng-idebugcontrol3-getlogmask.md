---
UID : NF:dbgeng.IDebugControl3.GetLogMask
title : IDebugControl3::GetLogMask method
author : windows-driver-content
description : The GetLogMask method returns the output mask for the currently open log file.
old-location : debugger\getlogmask.htm
old-project : debugger
ms.assetid : 32d36b6d-9887-43ac-9314-fc682705131e
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : dbgeng/IDebugControl::GetLogMask, dbgeng/IDebugControl3::GetLogMask, GetLogMask, GetLogMask method [Windows Debugging], IDebugControl interface, IDebugControl interface [Windows Debugging], GetLogMask method, IDebugControl::GetLogMask, debugger.getlogmask, dbgeng/IDebugControl2::GetLogMask, IDebugControl_a3ef306a-5134-49c7-b589-65a4afaa90ac.xml, GetLogMask method [Windows Debugging], IDebugControl3 interface, GetLogMask method [Windows Debugging], IDebugControl2 interface, IDebugControl3 interface [Windows Debugging], GetLogMask method, GetLogMask method [Windows Debugging], IDebugControl3, IDebugControl2 interface [Windows Debugging], GetLogMask method, IDebugControl3::GetLogMask, IDebugControl2::GetLogMask
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


# GetLogMask method
The <b>GetLogMask</b> method returns the output mask for the currently open log file.

## Syntax

````
HRESULT GetLogMask(
  [out] PULONG Mask
);
````

## Parameters

`Mask`

Receives the output mask for the log file.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for details about how to interpret this value.


## Return Value

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
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

For more information about log files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556734">SetLogMask</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetLogMask method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>