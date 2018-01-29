---
UID : NE:rilapitypes.RILCALLRTTMODE
title : RILCALLRTTMODE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcallrttmode_2.htm
old-project : netvista
ms.assetid : 89eaa5c2-2178-4181-bf3b-b10d179bc0eb
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILCALLRTTMODE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RILCALLRTTMODE, RILCALLRTTMODE, RIL_RTTMODE_FULL, RIL_RTTMODE_MAX, rilapitypes/RIL_RTTMODE_MAX, rilapitypes/RIL_RTTMODE_FULL, netvista.rilcallrttmode_2
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
req.typenames : RILCALLRTTMODE
req.product : Windows 10 or later.
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
| **Header** | rilapitypes.h |