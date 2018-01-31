---
UID : NE:rilapitypes.RILCARDAPPADDEDPARAMMASK
title : RILCARDAPPADDEDPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcardappaddedparammask_2.htm
old-project : netvista
ms.assetid : 47726715-306c-4167-8080-65085d1e7f8f
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : rilapitypes/RILCARDAPPADDEDPARAMMASK, rilapitypes/RIL_PARAM_CARDAPPADDED_UICCAPPINFO, RILCARDAPPADDEDPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RILCARDAPPADDEDPARAMMASK, RIL_PARAM_CARDAPPADDED_UICCAPPINFO, netvista.rilcardappaddedparammask_2, rilapitypes/RIL_PARAM_CARDAPPADDED_ALL, RIL_PARAM_CARDAPPADDED_ALL
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : RILCARDAPPADDEDPARAMMASK
req.product : Windows 10 or later.
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
| **Header** | rilapitypes.h |