---
UID: NS:pepfx._PEP_ACPI_GPIO_RESOURCE
title: "_PEP_ACPI_GPIO_RESOURCE"
author: windows-driver-content
description: The PEP_ACPI_GPIO_RESOURCE structure describes the ACPI configuration for a general purpose input/output (GPIO) resource.
old-location: kernel\pep_acpi_gpio_resource.htm
old-project: kernel
ms.assetid: 1B8AD1A9-9EB0-49A8-B791-0453C768A974
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_ACPI_GPIO_RESOURCE, PEP_ACPI_GPIO_RESOURCE, PEP_ACPI_GPIO_RESOURCE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_GPIO_RESOURCE, PPEP_ACPI_GPIO_RESOURCE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_GPIO_RESOURCE, kernel.pep_acpi_gpio_resource, pepfx/PEP_ACPI_GPIO_RESOURCE, pepfx/PPEP_ACPI_GPIO_RESOURCE"
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
-	PEP_ACPI_GPIO_RESOURCE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_GPIO_RESOURCE, *PPEP_ACPI_GPIO_RESOURCE
---

# _PEP_ACPI_GPIO_RESOURCE structure
The <b>PEP_ACPI_GPIO_RESOURCE</b> structure describes the ACPI configuration for a general purpose input/output (GPIO) resource.

## Syntax
```
typedef struct _PEP_ACPI_GPIO_RESOURCE {
  PEP_ACPI_RESOURCE_TYPE      Type;
  PEP_ACPI_RESOURCE_FLAGS     Flags;
  KINTERRUPT_MODE             InterruptType;
  KINTERRUPT_POLARITY         InterruptPolarity;
  GPIO_PIN_CONFIG_TYPE        PinConfig;
  GPIO_PIN_IORESTRICTION_TYPE IoRestrictionType;
  USHORT                      DriveStrength;
  USHORT                      DebounceTimeout;
  PUSHORT                     PinTable;
  USHORT                      PinCount;
  UCHAR                       ResourceSourceIndex;
  PUNICODE_STRING             ResourceSourceName;
  PUCHAR                      VendorData;
  USHORT                      VendorDataLength;
} PEP_ACPI_GPIO_RESOURCE, *PPEP_ACPI_GPIO_RESOURCE;
```

## Members


`Type`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186693">PEP_ACPI_RESOURCE_TYPE</a> enumeration value that identifies the resource type for this ACPI resource.

`Flags`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186692">PEP_ACPI_RESOURCE_FLAGS</a> structure that describes the capabilities of this ACPI resource.

`InterruptType`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff554239">KINTERRUPT_MODE</a> enumeration value that identifies the interrupt type.

`InterruptPolarity`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff554243">KINTERRUPT_POLARITY</a> enumeration value that identifies how a device signals an interrupt request on an interrupt line.

`PinConfig`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186634">GPIO_PIN_CONFIG_TYPE</a> enumeration value that identifies the GPIO pin configuration type.

`IoRestrictionType`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186635">GPIO_PIN_IORESTRICTION_TYPE</a> enumeration value that identifies the type of IO that the pin supports.

`DriveStrength`

Specifies the output drive capability of the pin, in hundredths of milliamperes.

`DebounceTimeout`

Specifies the hardware debounce wait time, in hundredths of milliseconds.

`PinTable`

A list of pin numbers on the resource that are described by this descriptor.

`PinCount`

The number of pins in <b>PinTable</b>.

`ResourceSourceIndex`

This member is always zero.

`ResourceSourceName`

This member is always set to "ResourceConsumer."

`VendorData`

A pointer to a raw data buffer containing vendor-defined byte data to be decoded by the OS driver.

`VendorDataLength`

The size of the <b>VendorData</b> buffer.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186634">GPIO_PIN_CONFIG_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186635">GPIO_PIN_IORESTRICTION_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554239">KINTERRUPT_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554243">KINTERRUPT_POLARITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186692">PEP_ACPI_RESOURCE_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186693">PEP_ACPI_RESOURCE_TYPE</a>