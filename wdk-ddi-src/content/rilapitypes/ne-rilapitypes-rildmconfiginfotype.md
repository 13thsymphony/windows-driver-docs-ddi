---
UID : NE:rilapitypes.RILDMCONFIGINFOTYPE
title : RILDMCONFIGINFOTYPE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rildmconfiginfotype_2.htm
old-project : netvista
ms.assetid : 86f09204-5f4a-412d-a10b-4692e159ca1b
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : rilapitypes/RIL_DMCV_TYPE_DWORD, rilapitypes/RIL_DMCV_TYPE_BOOLEAN, RIL_DMCV_TYPE_STRING, RILDMCONFIGINFOTYPE, rilapitypes/RIL_DMCV_TYPE_STRING, rilapitypes/RIL_DMCV_TYPE_MAX, RIL_DMCV_TYPE_DWORD, netvista.rildmconfiginfotype_2, RIL_DMCV_TYPE_BOOLEAN, RIL_DMCV_TYPE_MAX, rilapitypes/RILDMCONFIGINFOTYPE, RILDMCONFIGINFOTYPE enumeration [Network Drivers Starting with Windows Vista]
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
req.typenames : RILDMCONFIGINFOTYPE
req.product : Windows 10 or later.
---

# RILDMCONFIGINFOTYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILDMCONFIGINFOTYPE { 
  RIL_DMCV_TYPE_BOOLEAN,
  RIL_DMCV_TYPE_DWORD,
  RIL_DMCV_TYPE_STRING,
  RIL_DMCV_TYPE_MAX
} RILDMCONFIGINFOTYPE;
````

## Constants

<table>

<tr>
<td>RIL_DMCV_TYPE_BOOLEAN</td>
<td></td>
</tr>

<tr>
<td>RIL_DMCV_TYPE_DWORD</td>
<td></td>
</tr>

<tr>
<td>RIL_DMCV_TYPE_MAX</td>
<td></td>
</tr>

<tr>
<td>RIL_DMCV_TYPE_NONE</td>
<td></td>
</tr>

<tr>
<td>RIL_DMCV_TYPE_STRING</td>
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