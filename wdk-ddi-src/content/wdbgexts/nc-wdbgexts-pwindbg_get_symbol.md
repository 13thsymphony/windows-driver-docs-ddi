---
UID: NC:wdbgexts.PWINDBG_GET_SYMBOL
title: PWINDBG_GET_SYMBOL
author: windows-driver-content
description: The PWINDBG_GET_SYMBOL (GetSymbol) function locates the symbol nearest to address.
old-location: debugger\getsymbol.htm
old-project: debugger
ms.assetid: bec1b12f-0bf7-4cdd-86fe-baec2316d3c8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetSymbol, GetSymbol callback function [Windows Debugging], PWINDBG_GET_SYMBOL, WdbgExts_Ref_a892aa24-d1ee-43f4-8fd5-ea8d00aa678a.xml, debugger.getsymbol, wdbgexts/GetSymbol
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	wdbgexts.h
api_name:
-	GetSymbol
product: Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---


# PWINDBG_GET_SYMBOL callback function
The <b>PWINDBG_GET_SYMBOL</b>  (<b>GetSymbol</b>) function locates the symbol nearest to <i>address</i>.

## Syntax

```
PWINDBG_GET_SYMBOL PwindbgGetSymbol;

void PwindbgGetSymbol(
  PVOID offset,
  PCHAR pchBuffer,
  ULONG_PTR *pDisplacement
)
{...}
```

## Parameters

`offset`

Specifies an address near the symbol you want located.

`pchBuffer`

Receives the name of the symbol found.

`*pDisplacement`

Specifies the displacement from the beginning of the symbol.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |