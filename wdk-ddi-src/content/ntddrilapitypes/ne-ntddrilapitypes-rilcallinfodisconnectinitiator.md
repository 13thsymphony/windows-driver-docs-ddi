---
UID : NE:ntddrilapitypes.RILCALLINFODISCONNECTINITIATOR
title : RILCALLINFODISCONNECTINITIATOR
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcallinfodisconnectinitiator.htm
old-project : netvista
ms.assetid : df3c3cb9-583c-4a6e-9477-843067865418
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILCALLINFODISCONNECTINITIATOR, RIL_DISCINIT_LOCAL, ntddrilapitypes/RILCALLINFODISCONNECTINITIATOR, ntddrilapitypes/RIL_DISCINIT_MAX, RIL_DISCINIT_REMOTE, ntddrilapitypes/RIL_DISCINIT_LOCAL, ntddrilapitypes/RIL_DISCINIT_REMOTE, netvista.rilcallinfodisconnectinitiator, RILCALLINFODISCONNECTINITIATOR enumeration [Network Drivers Starting with Windows Vista], RIL_DISCINIT_MAX
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
req.typenames : RILCALLINFODISCONNECTINITIATOR
---

# RILCALLINFODISCONNECTINITIATOR Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLINFODISCONNECTINITIATOR { 
  RIL_DISCINIT_LOCAL,
  RIL_DISCINIT_REMOTE,
  RIL_DISCINIT_MAX
} RILCALLINFODISCONNECTINITIATOR;
````

## Constants

<table>

<tr>
<td>RIL_DISCINIT_LOCAL</td>
<td></td>
</tr>

<tr>
<td>RIL_DISCINIT_MAX</td>
<td></td>
</tr>

<tr>
<td>RIL_DISCINIT_REMOTE</td>
<td></td>
</tr>

<tr>
<td>RIL_DISCINIT_UNKNOWN</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |