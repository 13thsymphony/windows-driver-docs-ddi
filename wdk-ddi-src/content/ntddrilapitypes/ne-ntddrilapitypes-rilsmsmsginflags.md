---
UID : NE:ntddrilapitypes.RILSMSMSGINFLAGS
title : RILSMSMSGINFLAGS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsmsmsginflags.htm
old-project : netvista
ms.assetid : aaa7967a-dfbc-4c4c-a309-095628fae6c0
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddrilapitypes/RIL_SMSMSGIN_IMS, RILSMSMSGINFLAGS enumeration [Network Drivers Starting with Windows Vista], RILSMSMSGINFLAGS, ntddrilapitypes/RILSMSMSGINFLAGS, RIL_SMSMSGIN_IMS, RIL_SMSMSGIN_ALL, netvista.rilsmsmsginflags, ntddrilapitypes/RIL_SMSMSGIN_ALL
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
req.typenames : RILSMSMSGINFLAGS
---

# RILSMSMSGINFLAGS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSMSMSGINFLAGS { 
  RIL_SMSMSGIN_IMS,
  RIL_SMSMSGIN_ALL
} RILSMSMSGINFLAGS;
````

## Constants

<table>

<tr>
<td>RIL_SMSMSGIN_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_SMSMSGIN_IMS</td>
<td></td>
</tr>

<tr>
<td>RIL_SMSMSGIN_NONE</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |