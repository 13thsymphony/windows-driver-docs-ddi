---
UID: NF:dbgeng.IDebugSystemObjects3.GetCurrentSystemServer
title: IDebugSystemObjects3::GetCurrentSystemServer method
author: windows-driver-content
description: Gets the server for the current process.
old-location: debugger\idebugsystemobjects3_getcurrentsystemserver.htm
old-project: debugger
ms.assetid: 7956E4F6-7FB5-4349-81D2-4953108557D2
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetCurrentSystemServer method [Windows Debugging], GetCurrentSystemServer method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentSystemServer,IDebugSystemObjects3.GetCurrentSystemServer, IDebugSystemObjects3, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentSystemServer method, IDebugSystemObjects3::GetCurrentSystemServer, dbgeng/IDebugSystemObjects3::GetCurrentSystemServer, debugger.idebugsystemobjects3_getcurrentsystemserver
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
-	IDebugSystemObjects3.GetCurrentSystemServer
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSystemObjects3::GetCurrentSystemServer method
Gets the server for the current process.

## Syntax

```
HRESULT GetCurrentSystemServer(
  PULONG64 Server
);
```

## Parameters

`Server`

A pointer to the returned server value.


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