---
UID: NF:dbgeng.IDebugClient4.StartServer
title: IDebugClient4::StartServer method
author: windows-driver-content
description: The StartServer method starts a debugging server.
old-location: debugger\startserver.htm
old-project: debugger
ms.assetid: 52b1c590-a62b-4e27-a267-1862cb76e6d4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDebugClient interface [Windows Debugging], StartServer method, IDebugClient2 interface [Windows Debugging], StartServer method, IDebugClient2::StartServer, IDebugClient3 interface [Windows Debugging], StartServer method, IDebugClient3::StartServer, IDebugClient4, IDebugClient4 interface [Windows Debugging], StartServer method, IDebugClient4::StartServer, IDebugClient5 interface [Windows Debugging], StartServer method, IDebugClient5::StartServer, IDebugClient::StartServer, IDebugClient_5ca142fb-bb02-4484-adf0-9337f53d0bdc.xml, StartServer method [Windows Debugging], StartServer method [Windows Debugging], IDebugClient interface, StartServer method [Windows Debugging], IDebugClient2 interface, StartServer method [Windows Debugging], IDebugClient3 interface, StartServer method [Windows Debugging], IDebugClient4 interface, StartServer method [Windows Debugging], IDebugClient5 interface, StartServer,IDebugClient4.StartServer, dbgeng/IDebugClient2::StartServer, dbgeng/IDebugClient3::StartServer, dbgeng/IDebugClient4::StartServer, dbgeng/IDebugClient5::StartServer, dbgeng/IDebugClient::StartServer, debugger.startserver
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
-	IDebugClient.StartServer
-	IDebugClient2.StartServer
-	IDebugClient3.StartServer
-	IDebugClient4.StartServer
-	IDebugClient5.StartServer
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# StartServer method
The <b>StartServer</b>  method starts a debugging server.

## Syntax

````
HRESULT StartServer(
  [in] PCSTR Options
);
````

## Parameters

`Options`

Specifies the connections options for this server.  These are the same options given to the <b>.server</b> debugger command or the WinDbg and CDB <b>-server</b> command-line option.  For details on the syntax of this string, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537823">Activating a Debugging Server</a>.


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

The server that is started will be accessible by other <a href="https://msdn.microsoft.com/13F9D82A-4C04-425A-A063-B349DB5C8E08">debuggers</a> through the transport specified in the <i>Options</i> parameter.

For more information about debugging servers, see Debugging Server and Debugging Client.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nf-dbgeng-debugconnect.md">DebugConnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553247">OutputServers</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::StartServer method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>