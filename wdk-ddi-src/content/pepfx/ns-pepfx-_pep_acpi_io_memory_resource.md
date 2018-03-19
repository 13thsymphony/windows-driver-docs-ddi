---
UID: NS:pepfx._PEP_ACPI_IO_MEMORY_RESOURCE
title: "_PEP_ACPI_IO_MEMORY_RESOURCE"
author: windows-driver-content
description: The PEP_ACPI_IO_MEMORY_RESOURCE structure describes an ACPI IO port descriptor resource.
old-location: kernel\pep_acpi_io_memory_resource.htm
old-project: kernel
ms.assetid: 7438C120-9CFB-4D5D-9323-8A5D84D02449
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_ACPI_IO_MEMORY_RESOURCE, PEP_ACPI_IO_MEMORY_RESOURCE, PEP_ACPI_IO_MEMORY_RESOURCE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_IO_MEMORY_RESOURCE, PPEP_ACPI_IO_MEMORY_RESOURCE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_IO_MEMORY_RESOURCE, kernel.pep_acpi_io_memory_resource, pepfx/PEP_ACPI_IO_MEMORY_RESOURCE, pepfx/PPEP_ACPI_IO_MEMORY_RESOURCE"
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
-	PEP_ACPI_IO_MEMORY_RESOURCE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_IO_MEMORY_RESOURCE, *PPEP_ACPI_IO_MEMORY_RESOURCE
---

# _PEP_ACPI_IO_MEMORY_RESOURCE structure
The <b>PEP_ACPI_IO_MEMORY_RESOURCE</b> structure describes an ACPI IO port descriptor resource.

## Syntax
````
typedef struct _PEP_ACPI_IO_MEMORY_RESOURCE {
  PEP_ACPI_RESOURCE_TYPE Type;
  UCHAR                  Information;
  PHYSICAL_ADDRESS       MinimumAddress;
  PHYSICAL_ADDRESS       MaximumAddress;
  ULONG                  Alignment;
  ULONG                  Length;
} PEP_ACPI_IO_MEMORY_RESOURCE, *PPEP_ACPI_IO_MEMORY_RESOURCE;
````

## Members


`Type`

A <a href="..\pepfx\ne-pepfx-_pep_acpi_resource_type.md">PEP_ACPI_RESOURCE_TYPE</a> enumeration value that identifies the resource type for this ACPI resource.

`Information`

If bit 0 is a 1, this indicates that the logical device decodes 16-bit addresses. If bit 0 is 0, this indicates that the logical device only decodes the first 10 bits of the address.

Bits 1 to 7 of this member are reserved and must be set to zero.

`MinimumAddress`

Specifies the minimum acceptable starting address for the IO range.

`MaximumAddress`

Specifies the maximum acceptable starting address for the IO range.

`Alignment`

Specifies the alignment granularity for the IO address assigned.

`Length`

Specifies the number of bytes in the IO range.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="..\pepfx\ne-pepfx-_pep_acpi_resource_type.md">PEP_ACPI_RESOURCE_TYPE</a>