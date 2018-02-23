---
UID: NF:dbgeng.IDebugClient3.GetInputCallbacks
title: IDebugClient3::GetInputCallbacks method
author: windows-driver-content
description: The GetInputCallbacks method returns the input callbacks object registered with this client.
old-location: debugger\getinputcallbacks.htm
old-project: Debugger
ms.assetid: 1788d9b6-5e5e-48b6-b746-fd078768892f
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: dbgeng/IDebugClient2::GetInputCallbacks, IDebugClient2 interface [Windows Debugging], GetInputCallbacks method, GetInputCallbacks method [Windows Debugging], IDebugClient interface, GetInputCallbacks method [Windows Debugging], IDebugClient4 interface, IDebugClient4::GetInputCallbacks, GetInputCallbacks, IDebugClient5 interface [Windows Debugging], GetInputCallbacks method, IDebugClient, GetInputCallbacks method [Windows Debugging], IDebugClient2 interface, IDebugClient4 interface [Windows Debugging], GetInputCallbacks method, GetInputCallbacks method [Windows Debugging], IDebugClient5 interface, IDebugClient_ab365943-baaa-4a51-9c1b-d82086098b2f.xml, dbgeng/IDebugClient3::GetInputCallbacks, IDebugClient interface [Windows Debugging], GetInputCallbacks method, GetInputCallbacks method [Windows Debugging], IDebugClient3 interface [Windows Debugging], GetInputCallbacks method, IDebugClient2::GetInputCallbacks, IDebugClient5::GetInputCallbacks, dbgeng/IDebugClient5::GetInputCallbacks, dbgeng/IDebugClient4::GetInputCallbacks, IDebugClient2, IDebugClient::GetInputCallbacks, IDebugClient3::GetInputCallbacks, dbgeng/IDebugClient::GetInputCallbacks, debugger.getinputcallbacks, IDebugClient3, GetInputCallbacks method [Windows Debugging], IDebugClient3 interface
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
-	IDebugClient.GetInputCallbacks
-	IDebugClient2.GetInputCallbacks
-	IDebugClient3.GetInputCallbacks
-	IDebugClient4.GetInputCallbacks
-	IDebugClient5.GetInputCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetInputCallbacks method
The <b>GetInputCallbacks</b> method returns the <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">input callbacks</a> object registered with this client.

## Syntax

````
HRESULT GetInputCallbacks(
  [out] PDEBUG_INPUT_CALLBACKS *Callbacks
);
````

## Parameters

`Callbacks`

Receives an interface pointer for the <a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a> object registered with the client.


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

Each client can have at most one <a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a> object registered with it to receive requests for input.

If no <b>IDebugInputCallbacks</b> object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.

The <b>IDebugInputCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugInputCallbacks</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called. 

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556721">SetInputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient::GetInputCallbacks method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>