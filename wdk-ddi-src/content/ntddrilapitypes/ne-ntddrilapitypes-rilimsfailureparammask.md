---
UID : NE:ntddrilapitypes.RILIMSFAILUREPARAMMASK
title : RILIMSFAILUREPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilimsfailureparammask.htm
old-project : netvista
ms.assetid : ba1542e9-da6f-4696-8f71-575000a7724e
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_PARAM_IMSFAILURE_ALL, RILIMSFAILUREPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_IMSFAILURE_ERRORCODE, ntddrilapitypes/RIL_PARAM_IMSFAILURE_MESSAGESUBTYPE, ntddrilapitypes/RIL_PARAM_IMSFAILURE_ERRORCODE, ntddrilapitypes/RIL_PARAM_IMSFAILURE_ALL, RIL_PARAM_IMSFAILURE_MESSAGESUBTYPE, RIL_PARAM_IMSFAILURE_MESSAGETYPE, ntddrilapitypes/RIL_PARAM_IMSFAILURE_MESSAGETYPE, netvista.rilimsfailureparammask, RIL_PARAM_IMSFAILURE_ERRORSTRING, ntddrilapitypes/RILIMSFAILUREPARAMMASK, RILIMSFAILUREPARAMMASK, ntddrilapitypes/RIL_PARAM_IMSFAILURE_ERRORSTRING
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
req.typenames : RILIMSFAILUREPARAMMASK
---

# RILIMSFAILUREPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILIMSFAILUREPARAMMASK { 
  RIL_PARAM_IMSFAILURE_MESSAGETYPE,
  RIL_PARAM_IMSFAILURE_MESSAGESUBTYPE,
  RIL_PARAM_IMSFAILURE_ERRORCODE,
  RIL_PARAM_IMSFAILURE_ERRORSTRING,
  RIL_PARAM_IMSFAILURE_ALL
} RILIMSFAILUREPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_IMSFAILURE_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_IMSFAILURE_ERRORCODE</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_IMSFAILURE_ERRORSTRING</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_IMSFAILURE_EXECUTOR</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_IMSFAILURE_MESSAGESUBTYPE</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_IMSFAILURE_MESSAGETYPE</td>
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