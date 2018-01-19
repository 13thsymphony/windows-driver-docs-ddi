---
UID : NE:ntddrilapitypes.RILCALLHANDOVERSTATEPARAMMASK
title : RILCALLHANDOVERSTATEPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcallhandoverstateparammask.htm
old-project : netvista
ms.assetid : 2534a05b-9e7f-4081-af61-721cd1fa82fc
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILCALLHANDOVERSTATEPARAMMASK, RILCALLHANDOVERSTATEPARAMMASK
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
req.alt-api : RILCALLHANDOVERSTATEPARAMMASK
req.alt-loc : ntddrilapitypes.h
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
req.typenames : RILCALLHANDOVERSTATEPARAMMASK
---

# RILCALLHANDOVERSTATEPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLHANDOVERSTATEPARAMMASK { 
  RIL_PARAM_HANDOVER_OLD_TYPE,
  RIL_PARAM_HANDOVER_NEW_TYPE,
  RIL_PARAM_HANDOVER_3GPPCAUSE,
  RIL_PARAM_HANDOVER_ALL
} RILCALLHANDOVERSTATEPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_HANDOVER_3GPPCAUSE</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_HANDOVER_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_HANDOVER_NEW_TYPE</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_HANDOVER_OLD_TYPE</td>
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