---
UID: NS:pep_x._PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
title: "_PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES"
author: windows-driver-content
description: The PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure is used in the process of converting ACPI resources to BIOS resources by one of the PEP initialization functions.
old-location: kernel\pep_acpi_request_convert_to_bios_resources.htm
old-project: kernel
ms.assetid: DF9FD748-88E8-4E32-B698-0E8A3BE319DB
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure [Kernel-Mode Driver Architecture], PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, kernel.pep_acpi_request_convert_to_bios_resources, pepfx/PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, pepfx/PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, *PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, *PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
---

# _PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure
The <b>PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES</b> structure is used in the process of converting ACPI resources to BIOS resources by one of the <a href="https://msdn.microsoft.com/1FBF406C-22C7-4D46-840C-9966C3515B63">PEP initialization functions</a>.

## Syntax
```
typedef struct _PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES {
  NTSTATUS           TranslationStatus;
  PPEP_ACPI_RESOURCE InputBuffer;
  SIZE_T             InputBufferSize;
  PVOID              OutputBuffer;
  SIZE_T             OutputBufferSize;
  ULONG              Flags;
} *PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES;
```

## Members


`TranslationStatus`

The result code from the resource translation call.

`InputBuffer`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186691">PEP_ACPI_RESOURCE</a> containing the input buffer.

`InputBufferSize`

The size of the input buffer.

`OutputBuffer`

A pointer to the output buffer containing the translated structure.

`OutputBufferSize`

The size of the output buffer.

`Flags`

The value contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186692">PEP_ACPI_RESOURCE_FLAGS</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/1FBF406C-22C7-4D46-840C-9966C3515B63">PEP initialization functions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186691">PEP_ACPI_RESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186692">PEP_ACPI_RESOURCE_FLAGS</a>