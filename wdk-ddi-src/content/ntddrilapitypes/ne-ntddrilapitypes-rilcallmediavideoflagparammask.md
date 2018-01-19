---
UID : NE:ntddrilapitypes.RILCALLMEDIAVIDEOFLAGPARAMMASK
title : RILCALLMEDIAVIDEOFLAGPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcallmediavideoflagparammask.htm
old-project : netvista
ms.assetid : cff507e4-d673-4608-9fd9-530ff7e26ffb
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILCALLMEDIAVIDEOFLAGPARAMMASK, RILCALLMEDIAVIDEOFLAGPARAMMASK
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddrilapitypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RILCALLMEDIAVIDEOFLAGPARAMMASK
req.alt-loc : ntddrilapitypes.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : RILCALLMEDIAVIDEOFLAGPARAMMASK
---

# RILCALLMEDIAVIDEOFLAGPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLMEDIAVIDEOFLAGPARAMMASK { 
  RIL_CALLMEDIAVIDEOFLAG_CAPABILITY_UNKNOWN,
  RIL_CALLMEDIAVIDEOFLAG_PAUSE,
  RIL_CALLMEDIAVIDEOFLAG_TEMPORARILY_UNAVAILABLE,
  RIL_CALLMEDIAVIDEOFLAG_ALL
} RILCALLMEDIAVIDEOFLAGPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_CALLMEDIAVIDEOFLAG_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_CALLMEDIAVIDEOFLAG_CAPABILITY_UNKNOWN</td>
<td></td>
</tr>

<tr>
<td>RIL_CALLMEDIAVIDEOFLAG_PAUSE</td>
<td></td>
</tr>

<tr>
<td>RIL_CALLMEDIAVIDEOFLAG_TEMPORARILY_UNAVAILABLE</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |