---
UID : NE:ntddrilapitypes.RILNITZNOTIFICATIONCAPS
title : RILNITZNOTIFICATIONCAPS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilnitznotificationcaps.htm
old-project : netvista
ms.assetid : fa678bfa-ebcc-4950-951a-47f9bba98131
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddrilapitypes/RIL_CAPS_NITZ_MAX, RILNITZNOTIFICATIONCAPS, RIL_CAPS_NITZ_ENABLED, ntddrilapitypes/RILNITZNOTIFICATIONCAPS, ntddrilapitypes/RIL_CAPS_NITZ_ENABLED, netvista.rilnitznotificationcaps, RILNITZNOTIFICATIONCAPS enumeration [Network Drivers Starting with Windows Vista], RIL_CAPS_NITZ_MAX
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
req.typenames : RILNITZNOTIFICATIONCAPS
---

# RILNITZNOTIFICATIONCAPS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILNITZNOTIFICATIONCAPS { 
  RIL_CAPS_NITZ_ENABLED,
  RIL_CAPS_NITZ_MAX
} RILNITZNOTIFICATIONCAPS;
````

## Constants

<table>

<tr>
<td>RIL_CAPS_NITZ_DISABLED</td>
<td></td>
</tr>

<tr>
<td>RIL_CAPS_NITZ_ENABLED</td>
<td></td>
</tr>

<tr>
<td>RIL_CAPS_NITZ_MAX</td>
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