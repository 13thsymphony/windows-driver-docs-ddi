---
UID : NE:ntddrilapitypes.RILOPENUICCLOGICALCHANNELPARAMMASK
title : RILOPENUICCLOGICALCHANNELPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilopenuicclogicalchannelparammask.htm
old-project : netvista
ms.assetid : 28512a46-506b-40c2-a14d-165823bf94fb
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILOPENUICCLOGICALCHANNELPARAMMASK, RILOPENUICCLOGICALCHANNELPARAMMASK
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
req.alt-api : RILOPENUICCLOGICALCHANNELPARAMMASK
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
req.typenames : RILOPENUICCLOGICALCHANNELPARAMMASK
---

# RILOPENUICCLOGICALCHANNELPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILOPENUICCLOGICALCHANNELPARAMMASK { 
  RIL_PARAM_OULC_SELECTRESPLENGTH,
  RIL_PARAM_OULC_SELECTRESPONSE,
  RIL_PARAM_OULC_ALL
} RILOPENUICCLOGICALCHANNELPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_OULC_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_OULC_SELECTRESPLENGTH</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_OULC_SELECTRESPONSE</td>
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