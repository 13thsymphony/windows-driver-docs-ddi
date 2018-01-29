---
UID : NE:ntddrilapitypes.RILCALLRTTMODE
title : RILCALLRTTMODE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcallrttmode.htm
old-project : netvista
ms.assetid : f4e796d6-2eff-43f6-8afd-b74e3136deb3
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILCALLRTTMODE enumeration [Network Drivers Starting with Windows Vista], RILCALLRTTMODE, RIL_RTTMODE_FULL, ntddrilapitypes/RIL_RTTMODE_MAX, RIL_RTTMODE_MAX, netvista.rilcallrttmode, ntddrilapitypes/RILCALLRTTMODE, ntddrilapitypes/RIL_RTTMODE_FULL
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
req.typenames : RILCALLRTTMODE
---

# RILCALLRTTMODE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLRTTMODE { 
  RIL_RTTMODE_FULL,
  RIL_RTTMODE_MAX
} RILCALLRTTMODE;
````

## Constants

<table>

<tr>
<td>RIL_RTTMODE_DISABLED</td>
<td></td>
</tr>

<tr>
<td>RIL_RTTMODE_FULL</td>
<td></td>
</tr>

<tr>
<td>RIL_RTTMODE_MAX</td>
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