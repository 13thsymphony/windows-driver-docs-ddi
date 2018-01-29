---
UID : NE:rilapitypes.RILALPHAIDENTIFIERPARAMMASK
title : RILALPHAIDENTIFIERPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilalphaidentifierparammask_2.htm
old-project : netvista
ms.assetid : 20ac3122-dece-48de-b29a-9d4f7e22c7e0
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : rilapitypes/RIL_PARAM_AI_REASON, rilapitypes/RILALPHAIDENTIFIERPARAMMASK, RILALPHAIDENTIFIERPARAMMASK, RILALPHAIDENTIFIERPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_AI_ALL, netvista.rilalphaidentifierparammask_2, RIL_PARAM_AI_REASON, rilapitypes/RIL_PARAM_AI_ALL
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
req.typenames : RILALPHAIDENTIFIERPARAMMASK
req.product : Windows 10 or later.
---

# RILALPHAIDENTIFIERPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILALPHAIDENTIFIERPARAMMASK { 
  RIL_PARAM_AI_REASON,
  RIL_PARAM_AI_ALL
} RILALPHAIDENTIFIERPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_AI_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_AI_REASON</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_AI_TYPE</td>
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