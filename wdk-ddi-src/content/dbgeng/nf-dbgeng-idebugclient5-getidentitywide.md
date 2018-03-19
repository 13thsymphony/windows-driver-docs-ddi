---
UID: NF:dbgeng.IDebugClient5.GetIdentityWide
title: IDebugClient5::GetIdentityWide method
author: windows-driver-content
description: The GetIdentityWide method returns a string describing the computer and user this client represents.
old-location: debugger\getidentitywide.htm
old-project: debugger
ms.assetid: 8e55f829-2f55-4b83-8e0d-2554246a5d59
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetIdentityWide method [Windows Debugging], GetIdentityWide method [Windows Debugging], IDebugClient5 interface, GetIdentityWide,IDebugClient5.GetIdentityWide, IDebugClient5, IDebugClient5 interface [Windows Debugging], GetIdentityWide method, IDebugClient5::GetIdentityWide, dbgeng/IDebugClient5::GetIdentityWide, debugger.getidentitywide
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
-	IDebugClient5.GetIdentityWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetIdentityWide method
The <b>GetIdentityWide</b> method returns a string describing the computer and user this client represents.

## Syntax

````
HRESULT GetIdentityWide(
  [out, optional] PWSTR  Buffer,
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

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553219">OutputIdentity</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>