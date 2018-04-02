---
UID: NS:pepfx._PEP_ACPI_RESOURCE_FLAGS
title: "_PEP_ACPI_RESOURCE_FLAGS"
author: windows-driver-content
description: The PEP_ACPI_RESOURCE_FLAGS structure contains flags describing an ACPI resource.
old-location: kernel\pep_acpi_resource_flags.htm
old-project: kernel
ms.assetid: 1BB4933B-2707-4350-8D9C-E0E25A85F5CB
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_ACPI_RESOURCE_FLAGS, PEP_ACPI_RESOURCE_FLAGS, PEP_ACPI_RESOURCE_FLAGS union [Kernel-Mode Driver Architecture], PPEP_ACPI_RESOURCE_FLAGS, PPEP_ACPI_RESOURCE_FLAGS union pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_RESOURCE_FLAGS, kernel.pep_acpi_resource_flags, pepfx/PEP_ACPI_RESOURCE_FLAGS, pepfx/PPEP_ACPI_RESOURCE_FLAGS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_RESOURCE_FLAGS
product:
- Windows
targetos: Windows
req.typenames: PEP_ACPI_RESOURCE_FLAGS, *PPEP_ACPI_RESOURCE_FLAGS
---

# _PEP_ACPI_RESOURCE_FLAGS structure
The <b>PEP_ACPI_RESOURCE_FLAGS</b> structure contains flags describing an ACPI resource.

## Syntax
```
typedef struct _PEP_ACPI_RESOURCE_FLAGS {
  ULONG  AsULong;
  struct {
    ULONG  : 1  AddressingMode;
    ULONG  : 26 Reserved;
    ULONG  : 1  ResourceUsage;
    ULONG  : 1  Shared;
    ULONG  : 1  SharedMode;
    ULONG  : 1  SlaveMode;
    ULONG  : 1  Wake;
  } DUMMYSTRUCTNAME;
} PEP_ACPI_RESOURCE_FLAGS, *PPEP_ACPI_RESOURCE_FLAGS;
```

## Members


`AsULong`

The consolidated values of the flags in <b>DUMMYSTRUCTNAME</b>.

`DUMMYSTRUCTNAME`

A structure containing ACPI resource flags.



#### Shared

When set, indicates that this is a shared device.



#### Wake

When set, indicates that this device can be woken from a low-power state.



#### ResourceUsage

When set, indicates that this device is in use.



#### SlaveMode

When set, indicates that this device is in slave mode.



#### AddressingMode

When set, indicates that this device is in addressing mode.



#### SharedMode

When set, indicates that this device is in shared mode.



#### Reserved

This member is reserved and should be set to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |