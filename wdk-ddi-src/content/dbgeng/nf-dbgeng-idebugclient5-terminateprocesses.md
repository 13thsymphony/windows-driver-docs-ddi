---
UID: NF:dbgeng.IDebugClient5.TerminateProcesses
title: IDebugClient5::TerminateProcesses method
author: windows-driver-content
description: The TerminateProcesses method attempts to terminate all processes in all targets.
old-location: debugger\terminateprocesses.htm
old-project: debugger
ms.assetid: e106a176-b7f9-4812-9995-a23246439b23
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient5, TerminateProcesses method [Windows Debugging], IDebugClient2 interface, IDebugClient2 interface [Windows Debugging], TerminateProcesses method, IDebugClient4::TerminateProcesses, TerminateProcesses method [Windows Debugging], IDebugClient3 interface, dbgeng/IDebugClient5::TerminateProcesses, TerminateProcesses method [Windows Debugging], IDebugClient interface [Windows Debugging], TerminateProcesses method, TerminateProcesses method [Windows Debugging], IDebugClient5 interface, IDebugClient3 interface [Windows Debugging], TerminateProcesses method, debugger.terminateprocesses, IDebugClient2, IDebugClient5 interface [Windows Debugging], TerminateProcesses method, IDebugClient4, IDebugClient_6bbf21ae-e69b-4f44-a4e7-9b5abe428903.xml, dbgeng/IDebugClient3::TerminateProcesses, TerminateProcesses method [Windows Debugging], IDebugClient4 interface, IDebugClient2::TerminateProcesses, IDebugClient3, TerminateProcesses method [Windows Debugging], IDebugClient interface, IDebugClient4 interface [Windows Debugging], TerminateProcesses method, IDebugClient5::TerminateProcesses, IDebugClient, IDebugClient::TerminateProcesses, dbgeng/IDebugClient::TerminateProcesses, dbgeng/IDebugClient2::TerminateProcesses, TerminateProcesses, dbgeng/IDebugClient4::TerminateProcesses, IDebugClient3::TerminateProcesses
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
-	dbgeng.h
apiname:
-	IDebugClient.TerminateProcesses
-	IDebugClient2.TerminateProcesses
-	IDebugClient3.TerminateProcesses
-	IDebugClient4.TerminateProcesses
-	IDebugClient5.TerminateProcesses
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# TerminateProcesses method
The <b>TerminateProcesses</b> method attempts to terminate all <a href="https://msdn.microsoft.com/6182ca34-ee5e-47e9-82fe-29266397e3a8">processes</a> in all targets.

## Syntax

````
HRESULT TerminateProcesses();
````

## Parameters

This function has no parameters.

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

Only live user-mode processes are terminated by this method.  For other targets, the target is detached from the debugger without terminating.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558866">TerminateCurrentProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563855">.kill (Kill Process)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541851">DetachProcesses</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::TerminateProcesses method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>