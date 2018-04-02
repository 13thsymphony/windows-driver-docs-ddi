---
UID: NF:dbgeng.IDebugClient.GetOutputWidth
title: IDebugClient::GetOutputWidth method
author: windows-driver-content
description: Gets the width of an output line for commands that produce formatted output.
old-location: debugger\idebugclient_getoutputwidth.htm
old-project: debugger
ms.assetid: FE76DA51-400E-4F64-B8D9-8738D2F5031A
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetOutputWidth method [Windows Debugging], GetOutputWidth method [Windows Debugging], IDebugClient interface, GetOutputWidth,IDebugClient.GetOutputWidth, IDebugClient, IDebugClient interface [Windows Debugging], GetOutputWidth method, IDebugClient::GetOutputWidth, dbgeng/IDebugClient::GetOutputWidth, debugger.idebugclient_getoutputwidth
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
-	dbgeng.h
api_name:
-	IDebugClient.GetOutputWidth
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugClient::GetOutputWidth method
Gets the width of an output line for
    commands that produce formatted output.

## Syntax

```
HRESULT GetOutputWidth(
  PULONG Columns
);
```

## Parameters

`Columns`

The number of columns in the output.


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

This setting is a suggestion that can be overridden by other settings.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>