---
UID : NE:ntddrilapitypes.RILRADIOSTATEITEMATTRIBUTES
title : RILRADIOSTATEITEMATTRIBUTES
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilradiostateitemattributes.htm
old-project : netvista
ms.assetid : 320ad6e2-0d11-4902-bfdb-8df201d4d5b7
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISWRITABLE, ntddrilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISWRITABLE, ntddrilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_HAVEOPTIONS, ntddrilapitypes/RILRADIOSTATEITEMATTRIBUTES, RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISDIRTY, RIL_RADIOSTATE_ITEM_ATTRIBUTE_HAVEOPTIONS, RIL_RADIOSTATE_ITEM_ATTRIBUTE_ALL, ntddrilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_ALL, netvista.rilradiostateitemattributes, RILRADIOSTATEITEMATTRIBUTES, RILRADIOSTATEITEMATTRIBUTES enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISDIRTY
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
req.typenames : RILRADIOSTATEITEMATTRIBUTES
---

# RILRADIOSTATEITEMATTRIBUTES Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILRADIOSTATEITEMATTRIBUTES { 
  RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISDIRTY,
  RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISWRITABLE,
  RIL_RADIOSTATE_ITEM_ATTRIBUTE_HAVEOPTIONS,
  RIL_RADIOSTATE_ITEM_ATTRIBUTE_ALL
} RILRADIOSTATEITEMATTRIBUTES;
````

## Constants

<table>

<tr>
<td>RIL_RADIOSTATE_ITEM_ATTRIBUTE_ALL</td>
<td></td>
</tr>

<tr>
<td>RIL_RADIOSTATE_ITEM_ATTRIBUTE_HAVEOPTIONS</td>
<td></td>
</tr>

<tr>
<td>RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISDIRTY</td>
<td></td>
</tr>

<tr>
<td>RIL_RADIOSTATE_ITEM_ATTRIBUTE_ISWRITABLE</td>
<td></td>
</tr>

<tr>
<td>RIL_RADIOSTATE_ITEM_ATTRIBUTE_NO_ATTRIBUTE</td>
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