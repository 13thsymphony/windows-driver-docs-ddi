---
UID : NE:rilapitypes.RILUICCCARDINFOPARAMMASK
title : RILUICCCARDINFOPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\riluicccardinfoparammask_2.htm
old-project : netvista
ms.assetid : f27c7f54-f939-4e9b-a27c-b0137fbb7cec
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILUICCCARDINFOPARAMMASK, RILUICCCARDINFOPARAMMASK
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : rilapitypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RILUICCCARDINFOPARAMMASK
req.alt-loc : rilapitypes.h
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
req.typenames : RILUICCCARDINFOPARAMMASK
req.product : Windows 10 or later.
---

# RILUICCCARDINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCCARDINFOPARAMMASK { 
  RIL_PARAM_CARDINFO_ICCID,
  RIL_PARAM_CARDINFO_NUMAPPS,
  RIL_PARAM_CARDINFO_APPINFO,
  RIL_PARAM_CARDINFO_ALL
} RILUICCCARDINFOPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_CARDINFO_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CARDINFO_APPINFO</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CARDINFO_ICCID</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CARDINFO_NUMAPPS</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |