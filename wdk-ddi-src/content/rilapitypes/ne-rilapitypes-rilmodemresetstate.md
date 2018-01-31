---
UID : NE:rilapitypes.RILMODEMRESETSTATE
title : RILMODEMRESETSTATE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmodemresetstate_2.htm
old-project : netvista
ms.assetid : 9cdc6548-393f-4af6-a8ee-bb96deb0f228
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_MODEMRESETSTATE_FAILED, rilapitypes/RIL_MODEMRESETSTATE_RECOVERED, rilapitypes/RIL_MODEMRESETSTATE_FAILED, RILMODEMRESETSTATE, netvista.rilmodemresetstate_2, RIL_MODEMRESETSTATE_RECOVERED, rilapitypes/RILMODEMRESETSTATE, rilapitypes/RIL_MODEMRESETSTATE_MAX, RILMODEMRESETSTATE enumeration [Network Drivers Starting with Windows Vista], RIL_MODEMRESETSTATE_MAX
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
req.typenames : RILMODEMRESETSTATE
req.product : Windows 10 or later.
---

# RILMODEMRESETSTATE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMODEMRESETSTATE { 
  RIL_MODEMRESETSTATE_RECOVERED,
  RIL_MODEMRESETSTATE_FAILED,
  RIL_MODEMRESETSTATE_MAX
} RILMODEMRESETSTATE;
````

## Constants

<table>

<tr>
<td>RIL_MODEMRESETSTATE_FAILED</td>
<td></td>
</tr>

<tr>
<td>RIL_MODEMRESETSTATE_MAX</td>
<td></td>
</tr>

<tr>
<td>RIL_MODEMRESETSTATE_RECOVERED</td>
<td></td>
</tr>

<tr>
<td>RIL_MODEMRESETSTATE_STARTED</td>
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