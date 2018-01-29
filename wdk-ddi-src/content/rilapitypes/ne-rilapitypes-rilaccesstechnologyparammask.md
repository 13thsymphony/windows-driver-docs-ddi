---
UID : NE:rilapitypes.RILACCESSTECHNOLOGYPARAMMASK
title : RILACCESSTECHNOLOGYPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilaccesstechnologyparammask_2.htm
old-project : netvista
ms.assetid : 9acb41d8-502f-404e-a03f-d222eff6d0ad
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILACCESSTECHNOLOGYPARAMMASK, rilapitypes/RIL_PARAM_ACCTECH_ALL, RILACCESSTECHNOLOGYPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_ACCTECH_SYSTEMKIND, rilapitypes/RILACCESSTECHNOLOGYPARAMMASK, RIL_PARAM_ACCTECH_SYSTEMKIND, RIL_PARAM_ACCTECH_ALL, netvista.rilaccesstechnologyparammask_2
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
req.typenames : RILACCESSTECHNOLOGYPARAMMASK
req.product : Windows 10 or later.
---

# RILACCESSTECHNOLOGYPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILACCESSTECHNOLOGYPARAMMASK { 
  RIL_PARAM_ACCTECH_SYSTEMKIND,
  RIL_PARAM_ACCTECH_ALL
} RILACCESSTECHNOLOGYPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_ACCTECH_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_ACCTECH_SYSTEMKIND</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_ACCTECH_SYSTEMTYPE</td>
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