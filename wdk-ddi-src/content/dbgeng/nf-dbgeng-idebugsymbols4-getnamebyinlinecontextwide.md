---
UID: NF:dbgeng.IDebugSymbols4.GetNameByInlineContextWide
title: IDebugSymbols4::GetNameByInlineContextWide method
author: windows-driver-content
description: Gets a name by inline context.
old-location: debugger\idebugsymbols4_getnamebyinlinecontextwide.htm
old-project: debugger
ms.assetid: D77F5755-75B0-48E6-BC5C-565022F884E1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetNameByInlineContextWide method [Windows Debugging], GetNameByInlineContextWide method [Windows Debugging], IDebugSymbols4 interface, GetNameByInlineContextWide,IDebugSymbols4.GetNameByInlineContextWide, IDebugSymbols4, IDebugSymbols4 interface [Windows Debugging], GetNameByInlineContextWide method, IDebugSymbols4::GetNameByInlineContextWide, dbgeng/IDebugSymbols4::GetNameByInlineContextWide, debugger.idebugsymbols4_getnamebyinlinecontextwide
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
-	IDebugSymbols4.GetNameByInlineContextWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbols4::GetNameByInlineContextWide method
Gets a name by inline context.

## Syntax

```
HRESULT GetNameByInlineContextWide(
  ULONG64  Offset,
  ULONG    InlineContext,
  PWSTR    NameBuffer,
  ULONG    NameBufferSize,
  PULONG   NameSize,
  PULONG64 Displacement
);
```

## Parameters

`Offset`

An offset for the inline context.

`InlineContext`

The inline context.

`NameBuffer`

A pointer an output buffer for a Unicode character string.

`NameBufferSize`

The size of the name buffer.

`NameSize`

A pointer to the length of the name.

`Displacement`

A pointer to the displacement value of the name.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/BE2734B5-1E67-4E38-B4DF-0C353BFB1F0B">IDebugSymbols4</a>