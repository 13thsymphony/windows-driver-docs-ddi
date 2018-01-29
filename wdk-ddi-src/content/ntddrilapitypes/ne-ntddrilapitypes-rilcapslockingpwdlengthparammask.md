---
UID : NE:ntddrilapitypes.RILCAPSLOCKINGPWDLENGTHPARAMMASK
title : RILCAPSLOCKINGPWDLENGTHPARAMMASK
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcapslockingpwdlengthparammask.htm
old-project : netvista
ms.assetid : c6e89030-835e-4f7f-8bec-6cd19f598f9d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddrilapitypes/RILCAPSLOCKINGPWDLENGTHPARAMMASK, RIL_PARAM_CLPL_ALL, netvista.rilcapslockingpwdlengthparammask, RILCAPSLOCKINGPWDLENGTHPARAMMASK, RIL_PARAM_CLPL_PASSWORDLENGTH, ntddrilapitypes/RIL_PARAM_CLPL_PASSWORDLENGTH, RILCAPSLOCKINGPWDLENGTHPARAMMASK enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_PARAM_CLPL_ALL
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
req.typenames : RILCAPSLOCKINGPWDLENGTHPARAMMASK
---

# RILCAPSLOCKINGPWDLENGTHPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCAPSLOCKINGPWDLENGTHPARAMMASK { 
  RIL_PARAM_CLPL_PASSWORDLENGTH,
  RIL_PARAM_CLPL_ALL
} RILCAPSLOCKINGPWDLENGTHPARAMMASK;
````

## Constants

<table>

<tr>
<td>RIL_PARAM_CLPL_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CLPL_FACILITY</td>
<td></td>
</tr>

<tr>
<td>RIL_PARAM_CLPL_PASSWORDLENGTH</td>
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