---
UID : NE:ntddrilapitypes.RILCARDAPPADDEDPARAMMASK
title : RILCARDAPPADDEDPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcardappaddedparammask.htm
old-project : netvista
ms.assetid : 6097b40d-2f86-4f87-bf57-191371ec943d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddrilapitypes/RIL_PARAM_CARDAPPADDED_UICCAPPINFO, RILCARDAPPADDEDPARAMMASK enumeration [Network Drivers Starting with Windows Vista], netvista.rilcardappaddedparammask, RILCARDAPPADDEDPARAMMASK, RIL_PARAM_CARDAPPADDED_UICCAPPINFO, ntddrilapitypes/RIL_PARAM_CARDAPPADDED_ALL, ntddrilapitypes/RILCARDAPPADDEDPARAMMASK, RIL_PARAM_CARDAPPADDED_ALL
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : RILCARDAPPADDEDPARAMMASK
---

# RILCARDAPPADDEDPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCARDAPPADDEDPARAMMASK { 
  RIL_PARAM_CARDAPPADDED_UICCAPPINFO,
  RIL_PARAM_CARDAPPADDED_ALL
} RILCARDAPPADDEDPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_CARDAPPADDED_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CARDAPPADDED_SLOTINDEX</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CARDAPPADDED_UICCAPPINFO</td>
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