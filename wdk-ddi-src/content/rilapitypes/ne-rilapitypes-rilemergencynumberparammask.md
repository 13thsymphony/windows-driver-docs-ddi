---
UID : NE:rilapitypes.RILEMERGENCYNUMBERPARAMMASK
title : RILEMERGENCYNUMBERPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilemergencynumberparammask_2.htm
old-project : netvista
ms.assetid : a59daf60-43d9-4fe4-af72-dc031f259133
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_PARAM_ENUM_UICC, RILEMERGENCYNUMBERPARAMMASK, rilapitypes/RIL_PARAM_ENUM_ALL, RIL_PARAM_ENUM_CATEGORY, netvista.rilemergencynumberparammask_2, rilapitypes/RIL_PARAM_ENUM_CATEGORY, RIL_PARAM_ENUM_NUMBER, rilapitypes/RIL_PARAM_ENUM_NUMBER, RIL_PARAM_ENUM_ALL, rilapitypes/RIL_PARAM_ENUM_UICC, RILEMERGENCYNUMBERPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RILEMERGENCYNUMBERPARAMMASK
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
req.typenames : RILEMERGENCYNUMBERPARAMMASK
req.product : Windows 10 or later.
---

# RILEMERGENCYNUMBERPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILEMERGENCYNUMBERPARAMMASK { 
  RIL_PARAM_ENUM_UICC,
  RIL_PARAM_ENUM_CATEGORY,
  RIL_PARAM_ENUM_NUMBER,
  RIL_PARAM_ENUM_ALL
} RILEMERGENCYNUMBERPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_ENUM_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_ENUM_CATEGORY</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_ENUM_EXECUTOR</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_ENUM_NUMBER</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_ENUM_UICC</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |