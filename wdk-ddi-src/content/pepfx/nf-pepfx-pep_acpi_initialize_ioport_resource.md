---
UID: NF:pepfx.PEP_ACPI_INITIALIZE_IOPORT_RESOURCE
title: PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_ioport_resource.htm
old-project: kernel
ms.assetid: E7F9F8EF-3FDC-41D9-BB89-9EB93ED1A504
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PEP_ACPI_INITIALIZE_IOPORT_RESOURCE, PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_ioport_resource, pepfx/PEP_ACPI_INITIALIZE_IOPORT_RESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_INITIALIZE_IOPORT_RESOURCE
product: Windows
targetos: Windows
req.typenames: PEP_WORK_TYPE, *PPEP_WORK_TYPE
---


# PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function
The <b>PEP_ACPI_INITIALIZE_IOPORT_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx-_pep_acpi_io_memory_resource.md">PEP_ACPI_IO_MEMORY_RESOURCE</a> structure.

## Syntax

````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_IOPORT_RESOURCE(
  _In_  UCHAR              Decode,
  _In_  USHORT             MinimumAddress,
  _In_  USHORT             MaximumAddress,
  _In_  UCHAR              Alignment,
  _In_  UCHAR              PortLength,
  _Out_ PPEP_ACPI_RESOURCE Resource
);
````

## Parameters

`Decode`

Specifies how to decode the resource address. If bit 0 is a 1, this indicates that the logical device decodes 16-bit addresses. If bit 0 is 0, this indicates that the logical device only decodes the first 10 bits of the address.

Bits 1 to 7 of this parameter are reserved and must be set to zero.

`MinimumAddress`

Specifies the minimum acceptable starting address for the IO range.

`MaximumAddress`

Specifies the maximum acceptable starting address for the IO range.

`Alignment`

Specifies the alignment granularity for the IO address assigned.

`PortLength`

Specifies the number of bytes in the IO range.

`Resource`

A pointer to the resource. The structure behind the pointer is of type <a href="..\pepfx\ns-pepfx-_pep_acpi_io_memory_resource.md">PEP_ACPI_IO_MEMORY_RESOURCE</a>.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10.  |
| **Target Platform** | Windows |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_acpi_io_memory_resource.md">PEP_ACPI_IO_MEMORY_RESOURCE</a>