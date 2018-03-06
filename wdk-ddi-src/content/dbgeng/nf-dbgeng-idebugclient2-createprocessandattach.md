---
UID: NF:dbgeng.IDebugClient2.CreateProcessAndAttach
title: IDebugClient2::CreateProcessAndAttach method
author: windows-driver-content
description: The CreateProcessAndAttach method creates a process from a specified command line, then attach to another user-mode process.
old-location: debugger\createprocessandattach.htm
old-project: debugger
ms.assetid: 1a92a823-ec50-406f-942c-c64fc820f9af
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateProcessAndAttach method [Windows Debugging], CreateProcessAndAttach method [Windows Debugging], IDebugClient interface, CreateProcessAndAttach method [Windows Debugging], IDebugClient2 interface, CreateProcessAndAttach method [Windows Debugging], IDebugClient3 interface, CreateProcessAndAttach method [Windows Debugging], IDebugClient4 interface, CreateProcessAndAttach method [Windows Debugging], IDebugClient5 interface, CreateProcessAndAttach,IDebugClient2.CreateProcessAndAttach, IDebugClient interface [Windows Debugging], CreateProcessAndAttach method, IDebugClient2, IDebugClient2 interface [Windows Debugging], CreateProcessAndAttach method, IDebugClient2::CreateProcessAndAttach, IDebugClient3 interface [Windows Debugging], CreateProcessAndAttach method, IDebugClient3::CreateProcessAndAttach, IDebugClient4 interface [Windows Debugging], CreateProcessAndAttach method, IDebugClient4::CreateProcessAndAttach, IDebugClient5 interface [Windows Debugging], CreateProcessAndAttach method, IDebugClient5::CreateProcessAndAttach, IDebugClient::CreateProcessAndAttach, IDebugClient_5ff3afdf-164e-4f2f-a625-389f3da41d24.xml, dbgeng/IDebugClient2::CreateProcessAndAttach, dbgeng/IDebugClient3::CreateProcessAndAttach, dbgeng/IDebugClient4::CreateProcessAndAttach, dbgeng/IDebugClient5::CreateProcessAndAttach, dbgeng/IDebugClient::CreateProcessAndAttach, debugger.createprocessandattach
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient.CreateProcessAndAttach
-	IDebugClient2.CreateProcessAndAttach
-	IDebugClient3.CreateProcessAndAttach
-	IDebugClient4.CreateProcessAndAttach
-	IDebugClient5.CreateProcessAndAttach
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# CreateProcessAndAttach method
The <b>CreateProcessAndAttach</b>  method creates a process from a specified command line, then attach to another user-mode process.  The created process is suspended and only allowed to execute when the attach has completed.  This allows rough synchronization when debugging both,  client and server processes.

## Syntax

````
HRESULT CreateProcessAndAttach(
  [in]           ULONG64 Server,
  [in, optional] PSTR    CommandLine,
  [in]           ULONG   CreateFlags,
  [in]           ULONG   ProcessId,
  [in]           ULONG   AttachFlags
);
````

## Parameters

`Server`

Specifies the process server to use to attach to the process.  If <i>Server</i> is zero, the engine will connect to the local process without using a process server.

`CommandLine`

Specifies the command line to execute to create the new process.  If <i>CommandLine</i> is <b>NULL</b>, then no process is created and these methods attach to an existing process, as <a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a> does.

`CreateFlags`

Specifies the flags to use when creating the process.  For details on these flags, see <a href="..\dbgeng\ns-dbgeng-_debug_create_process_options.md">DEBUG_CREATE_PROCESS_OPTIONS</a>.<b>CreateFlags</b>.

`ProcessId`

Specifies the process ID of the target process the debugger will attach to.  If <i>ProcessId</i> is zero, the debugger will attach to the process it created from <i>CommandLine</i>.

`AttachFlags`

Specifies the flags that control how the debugger attaches to the target process.  For details on these flags, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541454">DEBUG_ATTACH_XXX</a>.


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

This method is available only for live user-mode debugging.

If <i>CommandLine</i> is not <b>NULL</b> and <i>ProcessId</i> is not zero, then the engine will create the process in a suspended state.  The engine will resume this newly created process after it successfully connects to the process specified in <i>ProcessId</i>.

<div class="alert"><b>Note</b>    The engine doesn't completely attach to the process until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a> method has been called.  Only after the process has generated an event -- for example, the create-process event -- does it become available in the debugger session.</div>
<div> </div>
For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537786">AbandonCurrentProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558866">TerminateCurrentProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562135">.attach (Attach to Process)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539323">CreateProcess2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541846">DetachCurrentProcess</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548243">GetRunningProcessDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548265">GetRunningProcessSystemIds</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562280">.create (Create Process)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::CreateProcessAndAttach method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>