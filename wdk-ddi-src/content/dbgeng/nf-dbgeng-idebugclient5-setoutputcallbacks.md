---
UID: NF:dbgeng.IDebugClient5.SetOutputCallbacks
title: IDebugClient5::SetOutputCallbacks method
author: windows-driver-content
description: The SetOutputCallbacks method registers an output callbacks object with this client.
old-location: debugger\setoutputcallbacks.htm
old-project: debugger
ms.assetid: 2226804c-dbdd-4855-9ba5-7c1959941e59
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugClient interface [Windows Debugging], SetOutputCallbacks method, IDebugClient2 interface [Windows Debugging], SetOutputCallbacks method, IDebugClient2::SetOutputCallbacks, IDebugClient3 interface [Windows Debugging], SetOutputCallbacks method, IDebugClient3::SetOutputCallbacks, IDebugClient4 interface [Windows Debugging], SetOutputCallbacks method, IDebugClient4::SetOutputCallbacks, IDebugClient5, IDebugClient5 interface [Windows Debugging], SetOutputCallbacks method, IDebugClient5::SetOutputCallbacks, IDebugClient::SetOutputCallbacks, IDebugClient_b1da4bc1-b368-475e-bd13-021358f9d234.xml, SetOutputCallbacks method [Windows Debugging], SetOutputCallbacks method [Windows Debugging], IDebugClient interface, SetOutputCallbacks method [Windows Debugging], IDebugClient2 interface, SetOutputCallbacks method [Windows Debugging], IDebugClient3 interface, SetOutputCallbacks method [Windows Debugging], IDebugClient4 interface, SetOutputCallbacks method [Windows Debugging], IDebugClient5 interface, SetOutputCallbacks,IDebugClient5.SetOutputCallbacks, dbgeng/IDebugClient2::SetOutputCallbacks, dbgeng/IDebugClient3::SetOutputCallbacks, dbgeng/IDebugClient4::SetOutputCallbacks, dbgeng/IDebugClient5::SetOutputCallbacks, dbgeng/IDebugClient::SetOutputCallbacks, debugger.setoutputcallbacks
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
-	IDebugClient.SetOutputCallbacks
-	IDebugClient2.SetOutputCallbacks
-	IDebugClient3.SetOutputCallbacks
-	IDebugClient4.SetOutputCallbacks
-	IDebugClient5.SetOutputCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugClient5::SetOutputCallbacks method
The <b>SetOutputCallbacks</b> method registers an <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">output callbacks</a> object with this client.

## Syntax

```
HRESULT SetOutputCallbacks(
  PDEBUG_OUTPUT_CALLBACKS Callbacks
);
```

## Parameters

`Callbacks`

Specifies the interface pointer to the output callbacks object to register with this client.


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

Each client can have at most one <a href="https://msdn.microsoft.com/library/windows/hardware/ff550801">IDebugOutputCallbacks</a> or <b>IDebugOutputCallbacks</b> object registered with it for output.

The <b>IDebugOutputCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  <b>SetOutputCallbacks</b> and <b>SetOutputCAllbacksWide</b> call the <b>IUnknown::AddRef</b> method in the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this interface will be called the next time <b>SetOutputCallbacks</b> or <b>SetOutputCallbacksWide</b> is called on this client, or when this client is deleted. 

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548071">GetOutputCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550801">IDebugOutputCallbacks</a>