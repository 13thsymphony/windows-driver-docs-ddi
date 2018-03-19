---
UID: NS:pepfx._PEP_ACPI_INTERRUPT_RESOURCE
title: "_PEP_ACPI_INTERRUPT_RESOURCE"
author: windows-driver-content
description: The PEP_ACPI_INTERRUPT_RESOURCE structure describes an ACPI interrupt resource.
old-location: kernel\pep_acpi_interrupt_resource.htm
old-project: kernel
ms.assetid: B440AB0E-72CC-40F1-B77E-C12C84124737
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_ACPI_INTERRUPT_RESOURCE, PEP_ACPI_INTERRUPT_RESOURCE, PEP_ACPI_INTERRUPT_RESOURCE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_INTERRUPT_RESOURCE, PPEP_ACPI_INTERRUPT_RESOURCE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_INTERRUPT_RESOURCE, kernel.pep_acpi_interrupt_resource, pepfx/PEP_ACPI_INTERRUPT_RESOURCE, pepfx/PPEP_ACPI_INTERRUPT_RESOURCE"
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
-	PEP_ACPI_INTERRUPT_RESOURCE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_INTERRUPT_RESOURCE, *PPEP_ACPI_INTERRUPT_RESOURCE
---

# _PEP_ACPI_INTERRUPT_RESOURCE structure
The <b>PEP_ACPI_INTERRUPT_RESOURCE</b> structure describes an ACPI interrupt resource.

## Syntax
````
typedef struct _PEP_ACPI_INTERRUPT_RESOURCE {
  PEP_ACPI_RESOURCE_TYPE  Type;
  KINTERRUPT_MODE         InterruptType;
  KINTERRUPT_POLARITY     InterruptPolarity;
  PEP_ACPI_RESOURCE_FLAGS Flags;
  UCHAR                   Count;
  PULONG                  Pins;
} PEP_ACPI_INTERRUPT_RESOURCE, *PPEP_ACPI_INTERRUPT_RESOURCE;
````

## Members


`Type`

A <a href="..\pepfx\ne-pepfx-_pep_acpi_resource_type.md">PEP_ACPI_RESOURCE_TYPE</a> enumeration value describing this resource.

`InterruptType`

A <a href="..\wudfwdm\ne-wudfwdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a> enumeration value that identifies the interrupt type.

`InterruptPolarity`

A <a href="..\wdm\ne-wdm-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a> enumeration value that identifies how a device signals an interrupt request on an interrupt line.

`Flags`

A <a href="..\pepfx\ns-pepfx-_pep_acpi_resource_flags.md">PEP_ACPI_RESOURCE_FLAGS</a> structure that describes the capabilities of this ACPI resource.

`Count`

The count of items in the <b>Pins</b> array.

`Pins`

A list of pin numbers on the resource that are described by this descriptor.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="..\wdm\ne-wdm-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a>



<a href="..\wudfwdm\ne-wudfwdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_resource_flags.md">PEP_ACPI_RESOURCE_FLAGS</a>



<a href="..\pepfx\ne-pepfx-_pep_acpi_resource_type.md">PEP_ACPI_RESOURCE_TYPE</a>