---
UID: NS:acpitabl._LPI_STATE_DESCRIPTOR
title: _LPI_STATE_DESCRIPTOR
author: windows-driver-content
description: Defines an LPI state descriptor.
old-location: acpi\lpi_state_descriptor.htm
old-project: acpi
ms.assetid: B52012DB-922A-43A2-A175-7F7887C290F1
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: _LPI_STATE_DESCRIPTOR, *PLPI_STATE_DESCRIPTOR, LPI_STATE_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpitabl.h
req.include-header: Acpitabl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: LPI_STATE_DESCRIPTOR
req.alt-loc: acpitabl.h
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
req.typenames: *PLPI_STATE_DESCRIPTOR, LPI_STATE_DESCRIPTOR
---

# _LPI_STATE_DESCRIPTOR structure



## -description
Defines an LPI state descriptor.



## -syntax

````
typedef struct _LPI_STATE_DESCRIPTOR {
  ULONG           Type;
  ULONG           Length;
  USHORT          UniqueId;
  UCHAR           Reserved[2];
  LPI_STATE_FLAGS Flags;
  GEN_ADDR        EntryTrigger;
  ULONG           Residency;
  ULONG           Latency;
  GEN_ADDR        ResidencyCounter;
  ULONGLONG       ResidencyCounterFrequency;
} LPI_STATE_DESCRIPTOR, *PLPI_STATE_DESCRIPTOR;
````


## -struct-fields

### -field Type

The type.


### -field Length

The length.


### -field UniqueId

A unique ID.


### -field Reserved

Reserved.


### -field Flags

State flags.


### -field EntryTrigger

An entry trigger.


### -field Residency

A residency value.


### -field Latency

A latency value.


### -field ResidencyCounter

Residency counter.


### -field ResidencyCounterFrequency

Residency counter frequency. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Acpitabl.h (include Acpitabl.h)</dt>
</dl>
</td>
</tr>
</table>