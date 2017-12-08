---
UID: NE.ntddstor._STORAGE_ZONE_CONDITION
title: _STORAGE_ZONE_CONDITION
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\storage_zone_condition.htm
old-project: storage
ms.assetid: 57FF3890-6B37-45EB-BB02-22B2ADDFAA90
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _STORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_ZONE_CONDITION
req.alt-loc: Ntddstor.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# _STORAGE_ZONE_CONDITION enumeration



## -description

<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>



## -syntax

````
typedef enum _STORAGE_ZONE_CONDITION { 
  ZoneConditionConventional      = 0x00,
  ZoneConditionEmpty             = 0x01,
  ZoneConditionImplicitlyOpened  = 0x02,
  ZoneConditionExplicitlyOpened  = 0x03,
  ZoneConditionClosed            = 0x04,
  ZoneConditionReadOnly          = 0x0D,
  ZoneConditionFull              = 0x0E,
  ZoneConditionOffline           = 0x0F
} STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION;
````


## -enum-fields

### -field ZoneConditionConventional

N/A

### -field ZoneConditionEmpty

N/A

### -field ZoneConditionImplicitlyOpened

N/A

### -field ZoneConditionExplicitlyOpened

N/A

### -field ZoneConditionClosed

N/A

### -field ZoneConditionReadOnly

N/A

### -field ZoneConditionFull

N/A

### -field ZoneConditionOffline

N/A

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddstor.h</dt>
</dl>
</td>
</tr>
</table>