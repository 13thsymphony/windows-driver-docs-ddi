---
UID : NE:rilapitypes.RILMSGACKSTATUS
title : RILMSGACKSTATUS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmsgackstatus_2.htm
old-project : netvista
ms.assetid : 412d9a0b-429b-4ce5-bf74-f602533174d7
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : rilapitypes/RIL_MSGACKSTATUS_FAIL_MEM_FULL, RILMSGACKSTATUS, RIL_MSGACKSTATUS_ERROR, rilapitypes/RIL_MSGACKSTATUS_MAX, rilapitypes/RIL_MSGACKSTATUS_ERROR, netvista.rilmsgackstatus_2, RIL_MSGACKSTATUS_FAIL_MEM_FULL, RIL_MSGACKSTATUS_MAX, rilapitypes/RILMSGACKSTATUS, RILMSGACKSTATUS enumeration [Network Drivers Starting with Windows Vista]
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
req.typenames : RILMSGACKSTATUS
req.product : Windows 10 or later.
---

# RILMSGACKSTATUS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGACKSTATUS { 
  RIL_MSGACKSTATUS_FAIL_MEM_FULL,
  RIL_MSGACKSTATUS_ERROR,
  RIL_MSGACKSTATUS_MAX
} RILMSGACKSTATUS;
````

## Constants

<table>

<tr>
<td>RIL_MSGACKSTATUS_ERROR</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGACKSTATUS_FAIL_MEM_FULL</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGACKSTATUS_MAX</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGACKSTATUS_STORED</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |