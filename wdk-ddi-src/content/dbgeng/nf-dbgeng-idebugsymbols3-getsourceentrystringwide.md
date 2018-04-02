---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryStringWide
title: IDebugSymbols3::GetSourceEntryStringWide method
author: windows-driver-content
description: Queries symbol information and returns locations in the target's memory.
old-location: debugger\idebugsymbols3_getsourceentrystringwide.htm
old-project: debugger
ms.assetid: CDB72C6A-43E5-463B-97E5-44D22214C071
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetSourceEntryStringWide method [Windows Debugging], GetSourceEntryStringWide method [Windows Debugging], IDebugSymbols3 interface, GetSourceEntryStringWide,IDebugSymbols3.GetSourceEntryStringWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSourceEntryStringWide method, IDebugSymbols3::GetSourceEntryStringWide, dbgeng/IDebugSymbols3::GetSourceEntryStringWide, debugger.idebugsymbols3_getsourceentrystringwide
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
-	IDebugSymbols3.GetSourceEntryStringWide
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbols3::GetSourceEntryStringWide method
Queries symbol information and returns locations in the target's memory.

## Syntax

```
HRESULT GetSourceEntryStringWide(
  PDEBUG_SYMBOL_SOURCE_ENTRY Entry,
  ULONG                      Which,
  PWSTR                      Buffer,
  ULONG                      BufferSize,
  PULONG                     StringSize
);
```

## Parameters

`Entry`

An entry as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541680">DEBUG_SYMBOL_SOURCE_ENTRY</a> structure.

`Which`

A value that determines which types to return.

`Buffer`

A pointer to a Unicode character string buffer for the results.

`BufferSize`

The size of the buffer.

`StringSize`

Pointer to the size of the string.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

    This method can return multiple results for a source lookup. This allows for all possible results to be returned.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>