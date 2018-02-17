---
UID: NF:dbgeng.IDebugClient3.CreateProcessWide
title: IDebugClient3::CreateProcessWide method
author: windows-driver-content
description: The CreateProcessWide method creates a process from the specified command line.
old-location: debugger\createprocesswide.htm
old-project: debugger
ms.assetid: 2a45c971-3dad-47ad-a819-6f2c6e34ad37
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient3 interface [Windows Debugging], CreateProcessWide method, dbgeng/IDebugClient3::CreateProcessWide, IDebugClient3::CreateProcessWide, dbgeng/IDebugClient5::CreateProcessWide, CreateProcessWide method [Windows Debugging], IDebugClient3 interface, IDebugClient4 interface [Windows Debugging], CreateProcessWide method, IDebugClient4::CreateProcessWide, IDebugClient3, CreateProcessWide method [Windows Debugging], IDebugClient5 interface, CreateProcessWide method [Windows Debugging], IDebugClient4 interface, dbgeng/IDebugClient4::CreateProcessWide, IDebugClient5::CreateProcessWide, CreateProcessWide method [Windows Debugging], IDebugClient5 interface [Windows Debugging], CreateProcessWide method, debugger.createprocesswide, CreateProcessWide
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
-	IDebugClient3.CreateProcessWide
-	IDebugClient4.CreateProcessWide
-	IDebugClient5.CreateProcessWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# CreateProcessWide method
The <b>CreateProcessWide</b> method creates a process from the specified command line.

## Syntax

````
HRESULT CreateProcessWide(
  [in] ULONG64 Server,
  [in] PWSTR   CommandLine,
  [in] ULONG   CreateFlags
);
````

## Parameters

`Server`

Specifies the process server to use when attaching to the process.  If <i>Server</i> is zero, the engine will create a local process without using a process server.

`CommandLine`

Specifies the command line to execute to create the new process. The <b>CreateProcessWide</b> method might modify the contents of the string that you supply in this parameter. Therefore, this parameter cannot be a pointer to read-only memory (such as a const variable or a literal string). Passing a constant string in this parameter can lead to an access violation.

`CreateFlags`

Specifies the flags to use when creating the process.  For details on these flags, see the <b>CreateFlags</b> member of the <a href="..\dbgeng\ns-dbgeng-_debug_create_process_options.md">DEBUG_CREATE_PROCESS_OPTIONS</a> structure.


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

If <i>CreateFlags</i> contains either of the flags DEBUG_PROCESS or DEBUG_ONLY_THIS_PROCESS, the engine also attaches to the newly created process. This behavior is similar to that of <a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a> when its argument <i>ProcessId</i> is set to zero.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539323">CreateProcess2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562280">.create (Create Process)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient3::CreateProcessWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>