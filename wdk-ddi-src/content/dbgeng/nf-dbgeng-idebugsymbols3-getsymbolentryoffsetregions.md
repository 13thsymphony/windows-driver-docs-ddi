---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryOffsetRegions
title: IDebugSymbols3::GetSymbolEntryOffsetRegions method
author: windows-driver-content
description: Returns all the memory regions known to be associated with a symbol.
old-location: debugger\idebugsymbols3_getsymbolentryoffsetregions.htm
old-project: debugger
ms.assetid: 986774F6-5256-4703-990A-EAB4AB09AF55
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetSymbolEntryOffsetRegions method [Windows Debugging], GetSymbolEntryOffsetRegions method [Windows Debugging], IDebugSymbols3 interface, GetSymbolEntryOffsetRegions,IDebugSymbols3.GetSymbolEntryOffsetRegions, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSymbolEntryOffsetRegions method, IDebugSymbols3::GetSymbolEntryOffsetRegions, dbgeng/IDebugSymbols3::GetSymbolEntryOffsetRegions, debugger.idebugsymbols3_getsymbolentryoffsetregions
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
-	IDebugSymbols3.GetSymbolEntryOffsetRegions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbols3::GetSymbolEntryOffsetRegions method
Returns all the memory regions known to be associated
    with a symbol.

## Syntax

```
HRESULT GetSymbolEntryOffsetRegions(
  PDEBUG_MODULE_AND_ID Id,
  ULONG                Flags,
  PDEBUG_OFFSET_REGION Regions,
  ULONG                RegionsCount,
  PULONG               RegionsAvail
);
```

## Parameters

`Id`

The ID of a module as a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a> structure.

`Flags`

A bit-set that contains options that affect the behavior of this method.

`Regions`

The memory regions associated with the symbol.

`RegionsCount`

The number of regions associated with the symbol.

`RegionsAvail`

A pointer to the number of regions available to the symbol.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

This function returns all known memory regions that associated
    with a specified symbol.  Simple symbols have a single region that starts from their base. More complicated regions, such as functions that have multiple code areas, can have an arbitrarily
    large number of regions.

The quality of information returned is highly
    dependent on the symbolic information available.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/A39FF088-1AA3-4E2F-8EF6-AD7F79FBBC92">IDebugSymbols3::GetSourceEntryOffsetRegions</a>