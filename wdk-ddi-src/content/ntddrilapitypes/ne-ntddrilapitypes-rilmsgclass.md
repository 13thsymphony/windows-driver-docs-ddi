---
UID : NE:ntddrilapitypes.RILMSGCLASS
title : RILMSGCLASS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmsgclass.htm
old-project : netvista
ms.assetid : 2f7e2c4f-56bc-4efd-8911-5161b657dbea
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_MSGCLASS_OUTGOING, ntddrilapitypes/RIL_MSGCLASS_OUTGOING, ntddrilapitypes/RILMSGCLASS, netvista.rilmsgclass, RILMSGCLASS enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_MSGCLASS_BROADCAST, RILMSGCLASS, ntddrilapitypes/RIL_MSGCLASS_INCOMING, RIL_MSGCLASS_ALL, RIL_MSGCLASS_BROADCAST, RIL_MSGCLASS_INCOMING, ntddrilapitypes/RIL_MSGCLASS_ALL
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
req.typenames : RILMSGCLASS
---

# RILMSGCLASS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGCLASS { 
  RIL_MSGCLASS_INCOMING,
  RIL_MSGCLASS_OUTGOING,
  RIL_MSGCLASS_BROADCAST,
  RIL_MSGCLASS_ALL
} RILMSGCLASS;
````

## Constants

<table>

<tr>
<td>RIL_MSGCLASS_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGCLASS_BROADCAST</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGCLASS_INCOMING</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGCLASS_NONE</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGCLASS_OUTGOING</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |