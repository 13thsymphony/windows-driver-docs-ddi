---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryByToken
title: IDebugSymbols3::GetSymbolEntryByToken method
author: windows-driver-content
description: Looks up a symbol by using a managed metadata token.
old-location: debugger\idebugsymbols3_getsymbolentrybytoken.htm
old-project: debugger
ms.assetid: C5BAED6C-223F-4D1B-A9A4-323C93DD5AD9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetSymbolEntryByToken method [Windows Debugging], GetSymbolEntryByToken method [Windows Debugging], IDebugSymbols3 interface, GetSymbolEntryByToken,IDebugSymbols3.GetSymbolEntryByToken, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSymbolEntryByToken method, IDebugSymbols3::GetSymbolEntryByToken, dbgeng/IDebugSymbols3::GetSymbolEntryByToken, debugger.idebugsymbols3_getsymbolentrybytoken
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
-	IDebugSymbols3.GetSymbolEntryByToken
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbols3::GetSymbolEntryByToken method
Looks up a symbol by using a managed metadata token.

## Syntax

```
HRESULT GetSymbolEntryByToken(
  ULONG64              ModuleBase,
  ULONG                Token,
  PDEBUG_MODULE_AND_ID Id
);
```

## Parameters

`ModuleBase`

The base of the module.

`Token`

The token to use to look up the symbol.

`Id`

A pointer to the module as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a> structure.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>