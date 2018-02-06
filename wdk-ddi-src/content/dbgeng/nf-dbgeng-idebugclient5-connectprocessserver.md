---
UID: NF:dbgeng.IDebugClient5.ConnectProcessServer
title: IDebugClient5::ConnectProcessServer method
author: windows-driver-content
description: The ConnectProcessServer methods connect to a process server.
old-location: debugger\connectprocessserver.htm
old-project: debugger
ms.assetid: c5fd12eb-0779-400f-a271-84b7b379529f
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugClient2::ConnectProcessServer, dbgeng/IDebugClient3::ConnectProcessServer, ConnectProcessServer method [Windows Debugging], IDebugClient5 interface, IDebugClient3 interface [Windows Debugging], ConnectProcessServer method, dbgeng/IDebugClient4::ConnectProcessServer, ConnectProcessServer method [Windows Debugging], IDebugClient interface, IDebugClient2 interface [Windows Debugging], ConnectProcessServer method, IDebugClient5, IDebugClient3::ConnectProcessServer, IDebugClient5 interface [Windows Debugging], ConnectProcessServer method, ConnectProcessServer method [Windows Debugging], IDebugClient2 interface, ConnectProcessServer, debugger.connectprocessserver, ConnectProcessServer method [Windows Debugging], dbgeng/IDebugClient5::ConnectProcessServer, IDebugClient_519f5e11-6f3b-4469-8352-e6cd7c1ed384.xml, ConnectProcessServer method [Windows Debugging], IDebugClient4 interface, IDebugClient4::ConnectProcessServer, IDebugClient2::ConnectProcessServer, ConnectProcessServer method [Windows Debugging], IDebugClient3 interface, IDebugClient4 interface [Windows Debugging], ConnectProcessServer method, dbgeng/IDebugClient::ConnectProcessServer, IDebugClient interface [Windows Debugging], ConnectProcessServer method, IDebugClient5::ConnectProcessServer, IDebugClient::ConnectProcessServer
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
-	IDebugClient.ConnectProcessServer
-	IDebugClient2.ConnectProcessServer
-	IDebugClient3.ConnectProcessServer
-	IDebugClient4.ConnectProcessServer
-	IDebugClient5.ConnectProcessServer
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# ConnectProcessServer method
The <b>ConnectProcessServer</b>  methods connect to a <a href="https://msdn.microsoft.com/4cfad26c-d8c0-4f80-aa54-b9cadbc84df3">process server</a>.

## Syntax

````
HRESULT ConnectProcessServer(
  [in]  PCSTR    RemoteOptions,
  [out] PULONG64 Server
);
````

## Parameters

`RemoteOptions`

Specifies how the <a href="https://msdn.microsoft.com/e4d53375-c82e-493b-9ccb-444c211fbc79">debugger engine</a> will connect with the process server.  These are the same options passed to the <b>-premote</b> option on the WinDbg and CDB command lines.  For details on the syntax of this string, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537840">Activating a Smart Client</a>.

`Server`

Receives a handle for the process server.  This handle is used when creating or attaching to processes by using the process server.


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

For more information about process servers and remote debugging, see <a href="https://msdn.microsoft.com/ed7ea3dc-07d1-481c-90e0-7f0b0e77ad42">Process Servers, Kernel Connection Servers, and Smart Clients</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548243">GetRunningProcessDescription</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539323">CreateProcess2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542993">EndProcessServer</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548254">GetRunningProcessSystemIdByExecutableName</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548265">GetRunningProcessSystemIds</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541969">DisconnectProcessServer</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::ConnectProcessServer method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>