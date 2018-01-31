---
UID : NE:rilapitypes.RILEXECUTORFOCUSSTATEPARAMMASK
title : RILEXECUTORFOCUSSTATEPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilexecutorfocusstateparammask_2.htm
old-project : netvista
ms.assetid : 3c5d14cf-bfbc-439c-9ade-1a672f0b3fca
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILEXECUTORFOCUSSTATEPARAMMASK, rilapitypes/RIL_PARAM_EXECUTORFOCUSSTATE_ALL, rilapitypes/RIL_PARAM_EXECUTORFOCUSSTATE_STATE, RIL_PARAM_EXECUTORFOCUSSTATE_STATE, RIL_PARAM_EXECUTORFOCUSSTATE_ALL, netvista.rilexecutorfocusstateparammask_2, RILEXECUTORFOCUSSTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RILEXECUTORFOCUSSTATEPARAMMASK
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
req.typenames : RILEXECUTORFOCUSSTATEPARAMMASK
req.product : Windows 10 or later.
---

# RILEXECUTORFOCUSSTATEPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILEXECUTORFOCUSSTATEPARAMMASK { 
  RIL_PARAM_EXECUTORFOCUSSTATE_STATE,
  RIL_PARAM_EXECUTORFOCUSSTATE_ALL
} RILEXECUTORFOCUSSTATEPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_EXECUTORFOCUSSTATE_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_EXECUTORFOCUSSTATE_NUMEXECUTORS</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_EXECUTORFOCUSSTATE_STATE</td>
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