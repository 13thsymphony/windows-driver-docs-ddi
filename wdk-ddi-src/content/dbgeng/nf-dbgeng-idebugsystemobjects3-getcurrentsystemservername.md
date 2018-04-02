---
UID: NF:dbgeng.IDebugSystemObjects3.GetCurrentSystemServerName
title: IDebugSystemObjects3::GetCurrentSystemServerName method
author: windows-driver-content
description: Gets the server name for the current process.
old-location: debugger\idebugsystemobjects3_getcurrentsystemservername.htm
old-project: debugger
ms.assetid: 4E06AFD0-42D3-479F-B285-34919826F750
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetCurrentSystemServerName method [Windows Debugging], GetCurrentSystemServerName method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentSystemServerName,IDebugSystemObjects3.GetCurrentSystemServerName, IDebugSystemObjects3, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentSystemServerName method, IDebugSystemObjects3::GetCurrentSystemServerName, dbgeng/IDebugSystemObjects3::GetCurrentSystemServerName, debugger.idebugsystemobjects3_getcurrentsystemservername
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
-	Dbgeng.h
api_name:
-	IDebugSystemObjects3.GetCurrentSystemServerName
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSystemObjects3::GetCurrentSystemServerName method
Gets the server name for the current process.

## Syntax

```
HRESULT GetCurrentSystemServerName(
  PSTR   Buffer,
  ULONG  BufferSize,
  PULONG NameSize
);
```

## Parameters

`Buffer`

A pointer to an output buffer.

`BufferSize`

The size of the buffer.

`NameSize`

A pointer to the name size.


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


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550892">IDebugSystemObjects3</a>