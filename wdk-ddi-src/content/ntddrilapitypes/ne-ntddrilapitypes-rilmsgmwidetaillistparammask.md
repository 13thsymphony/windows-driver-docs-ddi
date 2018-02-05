---
UID : NE:ntddrilapitypes.RILMSGMWIDETAILLISTPARAMMASK
title : RILMSGMWIDETAILLISTPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmsgmwidetaillistparammask.htm
old-project : netvista
ms.assetid : cc13eebd-810c-44b0-8909-4a4c3fc5b320
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_PARAM_MWIDETAIL_DETAILITEMS, ntddrilapitypes/RIL_PARAM_MWIDETAIL_DETAILITEMS, ntddrilapitypes/RIL_PARAM_MWIDETAIL_REFNUM, ntddrilapitypes/RIL_PARAM_MWIDETAIL_NUMDETAILITEMS, RIL_PARAM_MWIDETAIL_ALL, ntddrilapitypes/RILMSGMWIDETAILLISTPARAMMASK, ntddrilapitypes/RIL_PARAM_MWIDETAIL_ALL, netvista.rilmsgmwidetaillistparammask, RIL_PARAM_MWIDETAIL_NUMDETAILITEMS, RIL_PARAM_MWIDETAIL_REFNUM, RILMSGMWIDETAILLISTPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RILMSGMWIDETAILLISTPARAMMASK
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
req.typenames : RILMSGMWIDETAILLISTPARAMMASK
---

# RILMSGMWIDETAILLISTPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGMWIDETAILLISTPARAMMASK { 
  RIL_PARAM_MWIDETAIL_REFNUM,
  RIL_PARAM_MWIDETAIL_NUMDETAILITEMS,
  RIL_PARAM_MWIDETAIL_DETAILITEMS,
  RIL_PARAM_MWIDETAIL_ALL
} RILMSGMWIDETAILLISTPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_MWIDETAIL_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_MWIDETAIL_DETAILITEMS</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_MWIDETAIL_EXECUTOR</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_MWIDETAIL_NUMDETAILITEMS</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_MWIDETAIL_REFNUM</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |