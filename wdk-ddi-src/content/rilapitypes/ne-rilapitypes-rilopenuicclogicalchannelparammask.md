---
UID : NE:rilapitypes.RILOPENUICCLOGICALCHANNELPARAMMASK
title : RILOPENUICCLOGICALCHANNELPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilopenuicclogicalchannelparammask_2.htm
old-project : netvista
ms.assetid : abce79d2-1eca-4d62-af4f-434596bfb718
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILOPENUICCLOGICALCHANNELPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RILOPENUICCLOGICALCHANNELPARAMMASK, rilapitypes/RILOPENUICCLOGICALCHANNELPARAMMASK, RIL_PARAM_OULC_ALL, RIL_PARAM_OULC_SELECTRESPONSE, rilapitypes/RIL_PARAM_OULC_ALL, RIL_PARAM_OULC_SELECTRESPLENGTH, rilapitypes/RIL_PARAM_OULC_SELECTRESPLENGTH, netvista.rilopenuicclogicalchannelparammask_2, rilapitypes/RIL_PARAM_OULC_SELECTRESPONSE
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
req.typenames : RILOPENUICCLOGICALCHANNELPARAMMASK
req.product : Windows 10 or later.
---

# RILOPENUICCLOGICALCHANNELPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILOPENUICCLOGICALCHANNELPARAMMASK { 
  RIL_PARAM_OULC_SELECTRESPLENGTH,
  RIL_PARAM_OULC_SELECTRESPONSE,
  RIL_PARAM_OULC_ALL
} RILOPENUICCLOGICALCHANNELPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_OULC_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_OULC_CHANNELID</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_OULC_SELECTRESPLENGTH</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_OULC_SELECTRESPONSE</td>
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