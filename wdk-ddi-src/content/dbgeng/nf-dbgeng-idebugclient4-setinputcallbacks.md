---
UID: NF:dbgeng.IDebugClient4.SetInputCallbacks
title: IDebugClient4::SetInputCallbacks method
author: windows-driver-content
description: The SetInputCallbacks method registers an input callbacks object with the client.
old-location: debugger\setinputcallbacks.htm
old-project: debugger
ms.assetid: 4fd7ba5f-c400-4f44-bebb-b52e9a579f99
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugClient interface [Windows Debugging], SetInputCallbacks method, IDebugClient2 interface [Windows Debugging], SetInputCallbacks method, IDebugClient2::SetInputCallbacks, IDebugClient3 interface [Windows Debugging], SetInputCallbacks method, IDebugClient3::SetInputCallbacks, IDebugClient4, IDebugClient4 interface [Windows Debugging], SetInputCallbacks method, IDebugClient4::SetInputCallbacks, IDebugClient5 interface [Windows Debugging], SetInputCallbacks method, IDebugClient5::SetInputCallbacks, IDebugClient::SetInputCallbacks, IDebugClient_fea0d021-69b2-462f-965f-455305fd5971.xml, SetInputCallbacks method [Windows Debugging], SetInputCallbacks method [Windows Debugging], IDebugClient interface, SetInputCallbacks method [Windows Debugging], IDebugClient2 interface, SetInputCallbacks method [Windows Debugging], IDebugClient3 interface, SetInputCallbacks method [Windows Debugging], IDebugClient4 interface, SetInputCallbacks method [Windows Debugging], IDebugClient5 interface, SetInputCallbacks,IDebugClient4.SetInputCallbacks, dbgeng/IDebugClient2::SetInputCallbacks, dbgeng/IDebugClient3::SetInputCallbacks, dbgeng/IDebugClient4::SetInputCallbacks, dbgeng/IDebugClient5::SetInputCallbacks, dbgeng/IDebugClient::SetInputCallbacks, debugger.setinputcallbacks
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
req.lib: 
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
-	IDebugClient.SetInputCallbacks
-	IDebugClient2.SetInputCallbacks
-	IDebugClient3.SetInputCallbacks
-	IDebugClient4.SetInputCallbacks
-	IDebugClient5.SetInputCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# SetInputCallbacks method
The <b>SetInputCallbacks</b> method registers an <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">input callbacks</a> object with the client.

## Syntax

````
HRESULT SetInputCallbacks(
  [in, optional] PDEBUG_INPUT_CALLBACKS Callbacks
);
````

## Parameters

`Callbacks`

Specifies the interface pointer to the input callbacks object to register with this client.


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

The <b>IDebugInputCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  <b>SetInputCallbacks</b> will call the <b>IUnknown::AddRef</b> method of the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this interface will be called the next time <b>SetInputCallbacks</b> is called on this client, or when this client is deleted.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546892">GetInputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>