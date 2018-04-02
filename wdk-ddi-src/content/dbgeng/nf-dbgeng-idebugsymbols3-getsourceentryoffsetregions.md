---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryOffsetRegions
title: IDebugSymbols3::GetSourceEntryOffsetRegions method
author: windows-driver-content
description: Returns all memory regions known to be associated with a source entry.
old-location: debugger\idebugsymbols3_getsourceentryoffsetregions.htm
old-project: debugger
ms.assetid: A39FF088-1AA3-4E2F-8EF6-AD7F79FBBC92
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetSourceEntryOffsetRegions method [Windows Debugging], GetSourceEntryOffsetRegions method [Windows Debugging], IDebugSymbols3 interface, GetSourceEntryOffsetRegions,IDebugSymbols3.GetSourceEntryOffsetRegions, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSourceEntryOffsetRegions method, IDebugSymbols3::GetSourceEntryOffsetRegions, dbgeng/IDebugSymbols3::GetSourceEntryOffsetRegions, debugger.idebugsymbols3_getsourceentryoffsetregions
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
-	IDebugSymbols3.GetSourceEntryOffsetRegions
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbols3::GetSourceEntryOffsetRegions method
Returns all memory regions known to be associated
    with a source entry.

## Syntax

```
HRESULT GetSourceEntryOffsetRegions(
  PDEBUG_SYMBOL_SOURCE_ENTRY Entry,
  ULONG                      Flags,
  PDEBUG_OFFSET_REGION       Regions,
  ULONG                      RegionsCount,
  PULONG                     RegionsAvail
);
```

## Parameters

`Entry`

An entry as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541680">DEBUG_SYMBOL_SOURCE_ENTRY</a> structure.

`Flags`

A bit-set that contains options that affect the behavior of this method.

`Regions`

The memory regions associated with the source entry.

`RegionsCount`

The number of regions associated with the entry.

`RegionsAvail`

A pointer to the number of regions available to the entry.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

This function returns all known memory regions that associated
    with a specified source entry.  Simple symbols have a single region that starts from their base. More complicated regions, such as functions that have multiple code areas, can have an arbitrarily
    large number of regions.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541680">DEBUG_SYMBOL_SOURCE_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/986774F6-5256-4703-990A-EAB4AB09AF55">IDebugSymbols3::GetSymbolEntryOffsetRegions</a>