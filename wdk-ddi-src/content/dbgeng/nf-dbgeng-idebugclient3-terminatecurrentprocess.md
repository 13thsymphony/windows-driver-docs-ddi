---
UID: NF:dbgeng.IDebugClient3.TerminateCurrentProcess
title: IDebugClient3::TerminateCurrentProcess method
author: windows-driver-content
description: The TerminateCurrentProcess method attempts to terminate the current process.
old-location: debugger\terminatecurrentprocess.htm
old-project: Debugger
ms.assetid: 8d3798f2-dd43-4703-bd33-8f2c3f738122
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugClient2 interface [Windows Debugging], TerminateCurrentProcess method, IDebugClient4::TerminateCurrentProcess, IDebugClient2::TerminateCurrentProcess, IDebugClient4 interface [Windows Debugging], TerminateCurrentProcess method, dbgeng/IDebugClient5::TerminateCurrentProcess, IDebugClient3 interface [Windows Debugging], TerminateCurrentProcess method, TerminateCurrentProcess method [Windows Debugging], IDebugClient5 interface, dbgeng/IDebugClient4::TerminateCurrentProcess, TerminateCurrentProcess method [Windows Debugging], IDebugClient2 interface, TerminateCurrentProcess method [Windows Debugging], IDebugClient4 interface, debugger.terminatecurrentprocess, IDebugClient3::TerminateCurrentProcess, IDebugClient_7129a1e4-f1a5-4dff-a45c-bf759ae410cf.xml, TerminateCurrentProcess method [Windows Debugging], IDebugClient5::TerminateCurrentProcess, TerminateCurrentProcess, TerminateCurrentProcess method [Windows Debugging], IDebugClient3 interface, IDebugClient5 interface [Windows Debugging], TerminateCurrentProcess method, IDebugClient2, IDebugClient3, dbgeng/IDebugClient3::TerminateCurrentProcess, dbgeng/IDebugClient2::TerminateCurrentProcess
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
-	IDebugClient2.TerminateCurrentProcess
-	IDebugClient3.TerminateCurrentProcess
-	IDebugClient4.TerminateCurrentProcess
-	IDebugClient5.TerminateCurrentProcess
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# TerminateCurrentProcess method
The <b>TerminateCurrentProcess</b> method attempts to terminate the current process.

## Syntax

````
HRESULT TerminateCurrentProcess();
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

Only live user-modeprocesses are terminated by this method.  For other targets, the target is detached from the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> without terminating.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541846">DetachCurrentProcess</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537786">AbandonCurrentProcess</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558867">TerminateProcesses</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563855">.kill (Kill Process)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563855">.kill (Kill Process)</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient2::TerminateCurrentProcess method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>