---
UID : NE:ntddrilapitypes.RILCONFPARTICIPANTSTATUSPARAMMASK
title : RILCONFPARTICIPANTSTATUSPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilconfparticipantstatusparammask.htm
old-project : netvista
ms.assetid : a168b84a-fb3b-4e03-bb28-888b80cca6c6
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_PARAM_CPS_PARTICIPANTOP, RILCONFPARTICIPANTSTATUSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_PARAM_CPS_ALL, ntddrilapitypes/RIL_PARAM_CPS_PARTICIPANTOP, RIL_PARAM_CPS_SIPSTATUS, RIL_PARAM_CPS_ADDRESS, ntddrilapitypes/RIL_PARAM_CPS_ADDRESS, RIL_PARAM_CPS_CALLTRANSFER, ntddrilapitypes/RIL_PARAM_CPS_SIPSTATUS, RIL_PARAM_CPS_ALL, RILCONFPARTICIPANTSTATUSPARAMMASK, RIL_PARAM_CPS_ID, ntddrilapitypes/RIL_PARAM_CPS_CALLTRANSFER, ntddrilapitypes/RILCONFPARTICIPANTSTATUSPARAMMASK, netvista.rilconfparticipantstatusparammask, ntddrilapitypes/RIL_PARAM_CPS_ID
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
req.typenames : RILCONFPARTICIPANTSTATUSPARAMMASK
---

# RILCONFPARTICIPANTSTATUSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCONFPARTICIPANTSTATUSPARAMMASK { 
  RIL_PARAM_CPS_ID,
  RIL_PARAM_CPS_CALLTRANSFER,
  RIL_PARAM_CPS_ADDRESS,
  RIL_PARAM_CPS_PARTICIPANTOP,
  RIL_PARAM_CPS_SIPSTATUS,
  RIL_PARAM_CPS_ALL
} RILCONFPARTICIPANTSTATUSPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_CPS_ADDRESS</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CPS_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CPS_CALLTRANSFER</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CPS_EXECUTOR</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CPS_ID</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CPS_PARTICIPANTOP</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CPS_SIPSTATUS</td>
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