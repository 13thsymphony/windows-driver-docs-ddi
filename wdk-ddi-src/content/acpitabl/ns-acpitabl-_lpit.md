---
UID: NS:acpitabl._LPIT
title: "_LPIT"
author: windows-driver-content
description: Defines an LPI ACPI table.
old-location: acpi\lpit.htm
old-project: acpi
ms.assetid: 351BC859-E703-4F75-B691-A503C08560CF
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PLPIT, LPIT structure [ACPI Devices], acpi.lpit, acpitabl/PLPIT, acpitabl/LPIT, _LPIT, *PLPIT, PLPIT structure pointer [ACPI Devices], LPIT
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
-	LPIT
product: Windows
targetos: Windows
req.typenames: LPIT, *PLPIT
---

# _LPIT structure
Defines an LPI ACPI table.

## Syntax
````
typedef struct _LPIT {
  DESCRIPTION_HEADER   Header;
  LPI_STATE_DESCRIPTOR LpiStates[ANYSIZE_ARRAY];
} LPIT, *PLPIT;
````

## Members


`Header`

A header.

`LpiStates`

An array of states.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | acpitabl.h (include Acpitabl.h) |