---
UID: NF:dbgeng.IDebugClient3.GetIdentity
title: IDebugClient3::GetIdentity method
author: windows-driver-content
description: The GetIdentity method returns a string describing the computer and user this client represents.
old-location: debugger\getidentity.htm
old-project: Debugger
ms.assetid: 1d4e7c69-bc32-43f6-b45b-fcee2e04dc26
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: dbgeng/IDebugClient4::GetIdentity, GetIdentity, IDebugClient4 interface [Windows Debugging], GetIdentity method, dbgeng/IDebugClient2::GetIdentity, GetIdentity method [Windows Debugging], IDebugClient5 interface, GetIdentity method [Windows Debugging], IDebugClient3 interface, IDebugClient3 interface [Windows Debugging], GetIdentity method, IDebugClient3::GetIdentity, IDebugClient::GetIdentity, IDebugClient2::GetIdentity, dbgeng/IDebugClient::GetIdentity, IDebugClient, IDebugClient4::GetIdentity, IDebugClient2 interface [Windows Debugging], GetIdentity method, IDebugClient_7c54bffa-5190-49f5-919d-16bfb851ae36.xml, GetIdentity method [Windows Debugging], IDebugClient interface, GetIdentity method [Windows Debugging], dbgeng/IDebugClient5::GetIdentity, IDebugClient interface [Windows Debugging], GetIdentity method, IDebugClient5::GetIdentity, GetIdentity method [Windows Debugging], IDebugClient4 interface, IDebugClient2, debugger.getidentity, GetIdentity method [Windows Debugging], IDebugClient2 interface, IDebugClient5 interface [Windows Debugging], GetIdentity method, IDebugClient3, dbgeng/IDebugClient3::GetIdentity
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
-	IDebugClient.GetIdentity
-	IDebugClient2.GetIdentity
-	IDebugClient3.GetIdentity
-	IDebugClient4.GetIdentity
-	IDebugClient5.GetIdentity
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetIdentity method
The <b>GetIdentity</b>  method returns a string describing the computer and user this client represents.

## Syntax

````
HRESULT GetIdentity(
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG IdentitySize
);
````

## Parameters

`Buffer`

Specifies the buffer to receive the string.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

`BufferSize`

Specifies the size of the buffer <i>Buffer</i>.

`IdentitySize`

Receives the size of the string. If <i>IdentitySize</i> is <b>NULL</b>, this information is not returned.


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
The method was successful

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The size of the string was greater than the size of the buffer, so it was truncated to fit into the buffer.

</td>
</tr>
</table>

## Remarks

The specific content of the string varies with the operating system.  If the client is remotely connected, some network information may also be present.

For more information about client objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">Client Objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553219">OutputIdentity</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient::GetIdentity method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>