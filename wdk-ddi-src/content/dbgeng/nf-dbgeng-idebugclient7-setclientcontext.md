---
UID: NF:dbgeng.IDebugClient7.SetClientContext
title: IDebugClient7::SetClientContext method
author: windows-driver-content
description: The SetClientContext method is reserved for internal use.
old-location: debugger\idebugclient7_setclientcontext.htm
old-project: debugger
ms.assetid: 235DA791-D4D1-486C-B136-3703E62E91E2
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugClient7, IDebugClient7 interface [Windows Debugging], SetClientContext method, IDebugClient7::SetClientContext, SetClientContext method [Windows Debugging], SetClientContext method [Windows Debugging], IDebugClient7 interface, SetClientContext,IDebugClient7.SetClientContext, dbgeng/IDebugClient7::SetClientContext, debugger.idebugclient7_setclientcontext
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
-	IDebugClient7.SetClientContext
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugClient7::SetClientContext method
The <b>SetClientContext</b> method is reserved for internal use.

## Syntax

```
HRESULT SetClientContext(
  PVOID Context,
  ULONG ContextSize
);
```

## Parameters

`Context`

The <b>SetClientContext</b> method is reserved for internal use.

`ContextSize`

The <b>SetClientContext</b> method is reserved for internal use.


## Return Value

The <b>SetClientContext</b> method is reserved for internal use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/69CE0535-3ADD-481C-A016-695A7303BBA5">DEBUG_CLIENT_CONTEXT</a>



<a href="https://msdn.microsoft.com/16FBD831-D7AE-4B10-B76E-6CA42C9CABEB">IDebugClient7</a>