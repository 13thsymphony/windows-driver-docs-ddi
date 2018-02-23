---
UID: NS:pep_x._PEP_ACPI_RESOURCE_FLAGS
title: "_PEP_ACPI_RESOURCE_FLAGS"
author: windows-driver-content
description: The PEP_ACPI_RESOURCE_FLAGS structure contains flags describing an ACPI resource.
old-location: kernel\pep_acpi_resource_flags.htm
old-project: kernel
ms.assetid: 1BB4933B-2707-4350-8D9C-E0E25A85F5CB
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PEP_ACPI_RESOURCE_FLAGS, pepfx/PEP_ACPI_RESOURCE_FLAGS, PPEP_ACPI_RESOURCE_FLAGS union pointer [Kernel-Mode Driver Architecture], PEP_ACPI_RESOURCE_FLAGS union [Kernel-Mode Driver Architecture], pepfx/PPEP_ACPI_RESOURCE_FLAGS, kernel.pep_acpi_resource_flags, _PEP_ACPI_RESOURCE_FLAGS, PPEP_ACPI_RESOURCE_FLAGS, *PPEP_ACPI_RESOURCE_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_ACPI_RESOURCE_FLAGS
product: Windows
targetos: Windows
req.typenames: "*PPEP_ACPI_RESOURCE_FLAGS, PEP_ACPI_RESOURCE_FLAGS"
---

# _PEP_ACPI_RESOURCE_FLAGS structure
The <b>PEP_ACPI_RESOURCE_FLAGS</b> structure contains flags describing an ACPI resource.

## Syntax
````
typedef union _PEP_ACPI_RESOURCE_FLAGS {
  ULONG  AsULong;
  struct {
    ULONG Shared  :1;
    ULONG Wake  :1;
    ULONG ResourceUsage  :1;
    ULONG SlaveMode  :1;
    ULONG AddressingMode  :1;
    ULONG SharedMode  :1;
    ULONG Reserved  :26;
  } DUMMYSTRUCTNAME;
} PEP_ACPI_RESOURCE_FLAGS, *PPEP_ACPI_RESOURCE_FLAGS;
````

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
| **Header** | pep_x.h (include Pep_x.h) |