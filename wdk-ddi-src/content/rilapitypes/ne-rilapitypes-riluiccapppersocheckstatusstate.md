---
UID : NE:rilapitypes.RILUICCAPPPERSOCHECKSTATUSSTATE
title : RILUICCAPPPERSOCHECKSTATUSSTATE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\riluiccapppersocheckstatusstate_2.htm
old-project : netvista
ms.assetid : 389c20de-7ff2-47c6-8393-529e401e56e0
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILUICCAPPPERSOCHECKSTATUSSTATE, RILUICCAPPPERSOCHECKSTATUSSTATE
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
req.alt-api : RILUICCAPPPERSOCHECKSTATUSSTATE
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
req.typenames : RILUICCAPPPERSOCHECKSTATUSSTATE
req.product : Windows 10 or later.
---

# RILUICCAPPPERSOCHECKSTATUSSTATE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCAPPPERSOCHECKSTATUSSTATE { 
  RIL_PERSOCHECKSTATE_PASS,
  RIL_PERSOCHECKSTATE_FAIL,
  RIL_PERSOCHECKSTATE_MAX
} RILUICCAPPPERSOCHECKSTATUSSTATE;
````

## Constants

<table>

<tr>
<td>RIL_PERSOCHECKSTATE_FAIL</td>
<td></td>
</tr>

<tr>
<td>RIL_PERSOCHECKSTATE_MAX</td>
<td></td>
</tr>

<tr>
<td>RIL_PERSOCHECKSTATE_PASS</td>
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