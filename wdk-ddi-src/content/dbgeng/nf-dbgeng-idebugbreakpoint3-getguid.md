---
UID: NF:dbgeng.IDebugBreakpoint3.GetGuid
title: IDebugBreakpoint3::GetGuid method
author: windows-driver-content
description: Returns a GUID for the breakpoint.
old-location: debugger\idebugbreakpoint3_getguid.htm
old-project: debugger
ms.assetid: 0D279F79-FFA8-4661-A9E9-EFA62A97EEC7
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetGuid method [Windows Debugging], GetGuid method [Windows Debugging], IDebugBreakpoint3 interface, GetGuid,IDebugBreakpoint3.GetGuid, IDebugBreakpoint3, IDebugBreakpoint3 interface [Windows Debugging], GetGuid method, IDebugBreakpoint3::GetGuid, dbgeng/IDebugBreakpoint3::GetGuid, debugger.idebugbreakpoint3_getguid
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
-	IDebugBreakpoint3.GetGuid
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugBreakpoint3::GetGuid method
Returns a GUID for the breakpoint.

## Syntax

```
HRESULT GetGuid(
  LPGUID Guid
);
```

## Parameters

`Guid`

A unique ID returned for the breakpoint.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/42A31C23-9C02-48F6-83CC-CA017F76DE18">IDebugBreakpoint3</a>