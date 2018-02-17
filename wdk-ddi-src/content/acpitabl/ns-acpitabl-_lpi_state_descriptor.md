---
UID: NS:acpitabl._LPI_STATE_DESCRIPTOR
title: "_LPI_STATE_DESCRIPTOR"
author: windows-driver-content
description: Defines an LPI state descriptor.
old-location: acpi\lpi_state_descriptor.htm
old-project: acpi
ms.assetid: B52012DB-922A-43A2-A175-7F7887C290F1
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: LPI_STATE_DESCRIPTOR, PLPI_STATE_DESCRIPTOR structure pointer [ACPI Devices], PLPI_STATE_DESCRIPTOR, acpitabl/LPI_STATE_DESCRIPTOR, acpi.lpi_state_descriptor, LPI_STATE_DESCRIPTOR structure [ACPI Devices], *PLPI_STATE_DESCRIPTOR, acpitabl/PLPI_STATE_DESCRIPTOR, _LPI_STATE_DESCRIPTOR
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	acpitabl.h
apiname:
-	LPI_STATE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PLPI_STATE_DESCRIPTOR, LPI_STATE_DESCRIPTOR"
---

# _LPI_STATE_DESCRIPTOR structure
Defines an LPI state descriptor.

## Syntax
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

## Members


`EntryTrigger`

An entry trigger.

`Flags`

State flags.

`Latency`

A latency value.

`Length`

The length.

`Reserved`

Reserved.

`Residency`

A residency value.

`ResidencyCounter`

Residency counter.

`ResidencyCounterFrequency`

Residency counter frequency.

`Type`

The type.

`UniqueId`

A unique ID.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | acpitabl.h (include Acpitabl.h) |