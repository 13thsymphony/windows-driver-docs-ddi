---
UID: NF:dbgeng.IDebugClient4.OutputIdentity
title: IDebugClient4::OutputIdentity method
author: windows-driver-content
description: The OutputIdentity method formats and outputs a string describing the computer and user this client represents.
old-location: debugger\outputidentity.htm
old-project: debugger
ms.assetid: 0e8ced7c-87f3-4366-8137-b0d19dffc340
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugClient interface [Windows Debugging], OutputIdentity method, IDebugClient2 interface [Windows Debugging], OutputIdentity method, IDebugClient2::OutputIdentity, IDebugClient3 interface [Windows Debugging], OutputIdentity method, IDebugClient3::OutputIdentity, IDebugClient4, IDebugClient4 interface [Windows Debugging], OutputIdentity method, IDebugClient4::OutputIdentity, IDebugClient5 interface [Windows Debugging], OutputIdentity method, IDebugClient5::OutputIdentity, IDebugClient::OutputIdentity, IDebugClient_2013e1cd-3c95-4ef7-a53f-004ba30d9ea2.xml, OutputIdentity method [Windows Debugging], OutputIdentity method [Windows Debugging], IDebugClient interface, OutputIdentity method [Windows Debugging], IDebugClient2 interface, OutputIdentity method [Windows Debugging], IDebugClient3 interface, OutputIdentity method [Windows Debugging], IDebugClient4 interface, OutputIdentity method [Windows Debugging], IDebugClient5 interface, OutputIdentity,IDebugClient4.OutputIdentity, dbgeng/IDebugClient2::OutputIdentity, dbgeng/IDebugClient3::OutputIdentity, dbgeng/IDebugClient4::OutputIdentity, dbgeng/IDebugClient5::OutputIdentity, dbgeng/IDebugClient::OutputIdentity, debugger.outputidentity
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
-	IDebugClient.OutputIdentity
-	IDebugClient2.OutputIdentity
-	IDebugClient3.OutputIdentity
-	IDebugClient4.OutputIdentity
-	IDebugClient5.OutputIdentity
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# OutputIdentity method
The <b>OutputIdentity</b> method formats and outputs a string describing the computer and user this client represents.

## Syntax

````
HRESULT OutputIdentity(
  [in] ULONG OutputControl,
  [in] ULONG Flags,
  [in] PCSTR Format
);
````

## Parameters

`OutputControl`

Specifies where to send the output.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.

`Flags`

Set to zero.

`Format`

Specifies a format string similar to the <b>printf</b> format string.  However, this format string must only contain one formatting directive, <b>%s</b>, which will be replaced by a description of the computer and user this client represents.


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

The specific content of the string varies with the operating system.  If the client is remotely connected, some network information may also be present.

For more information about client objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">Client Objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546831">GetIdentity</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>