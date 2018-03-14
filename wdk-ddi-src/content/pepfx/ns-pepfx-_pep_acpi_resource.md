---
UID: NS:pepfx._PEP_ACPI_RESOURCE
title: "_PEP_ACPI_RESOURCE"
author: windows-driver-content
description: The PEP_ACPI_RESOURCE structure contains hardware details for a specific ACPI resource.
old-location: kernel\pep_acpi_resource.htm
old-project: kernel
ms.assetid: 534F736D-906C-48B5-9CEE-0E37459DA03F
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_ACPI_RESOURCE, PEP_ACPI_RESOURCE, PEP_ACPI_RESOURCE union [Kernel-Mode Driver Architecture], PPEP_ACPI_RESOURCE, PPEP_ACPI_RESOURCE union pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_RESOURCE, kernel.pep_acpi_resource, pepfx/PEP_ACPI_RESOURCE, pepfx/PPEP_ACPI_RESOURCE"
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
-	PEP_ACPI_RESOURCE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_RESOURCE, *PPEP_ACPI_RESOURCE
---

# _PEP_ACPI_RESOURCE structure
The <b>PEP_ACPI_RESOURCE</b> structure contains hardware details for a specific ACPI resource.

## Syntax
````
typedef union _PEP_ACPI_RESOURCE {
  PEP_ACPI_RESOURCE_TYPE      Type;
  PEP_ACPI_IO_MEMORY_RESOURCE IoMemory;
  PEP_ACPI_INTERRUPT_RESOURCE Interrupt;
  PEP_ACPI_GPIO_RESOURCE      Gpio;
  PEP_ACPI_SPB_I2C_RESOURCE   SpbI2c;
  PEP_ACPI_SPB_SPI_RESOURCE   SpbSpi;
  PEP_ACPI_SPB_UART_RESOURCE  SpbUart;
  PEP_ACPI_EXTENDED_ADDRESS   ExtendedAddress;
} PEP_ACPI_RESOURCE, *PPEP_ACPI_RESOURCE;
````

## Members


`ExtendedAddress`

If <b>Type</b> is <b>PepAcpiExtendedMemory</b> or <b>PepAcpiExtendedIo</b>, this union contains a <a href="..\pepfx\ns-pepfx-_pep_acpi_extended_address.md">PEP_ACPI_EXTENDED_ADDRESS</a> structure describing an ACPI extended memory or extended IO resource.

`Gpio`

If <b>Type</b> is <b>PepAcpiGpioIo</b> or <b>PepAcpiGpioInt</b>, this union contains a <a href="..\pepfx\ns-pepfx-_pep_acpi_gpio_resource.md">PEP_ACPI_GPIO_RESOURCE</a> structure describing an ACPI GPIO resource.

`Interrupt`

If <b>Type</b> is <b>PepAcpiInterrupt</b>, this union contains a <a href="..\pepfx\ns-pepfx-_pep_acpi_interrupt_resource.md">PEP_ACPI_INTERRUPT_RESOURCE</a> structure describing an ACPI interrupt resource.

`IoMemory`

If <b>Type</b> is <b>PepAcpiMemory</b> or <b>PepAcpiIoPort</b>, this union contains a <a href="..\pepfx\ns-pepfx-_pep_acpi_io_memory_resource.md">PEP_ACPI_IO_MEMORY_RESOURCE</a> structure describing an ACPI IO or memory resource.

`SpbI2c`

If <b>Type</b> is <b>PepAcpiSpbI2c</b>, this union contains a <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_i2c_resource.md">PEP_ACPI_SPB_I2C_RESOURCE</a> structure describing an ACPI I2C serial bus resource.

`SpbSpi`

If <b>Type</b> is <b>PepAcpiSpbSpi</b>, this union contains a <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_spi_resource.md">PEP_ACPI_SPB_SPI_RESOURCE</a> structure describing an ACPI SPI serial bus resource.

`SpbUart`

If <b>Type</b> is <b>PepAcpiSpbUart</b>, this union contains a <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_uart_resource.md">PEP_ACPI_SPB_UART_RESOURCE</a> structure describing an ACPI SPB serial bus resource.

`Type`

The <a href="..\pepfx\ne-pepfx-_pep_acpi_resource_type.md">PEP_ACPI_RESOURCE_TYPE</a> enumeration value that is applicable to  this resource.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_acpi_gpio_resource.md">PEP_ACPI_GPIO_RESOURCE</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_spb_i2c_resource.md">PEP_ACPI_SPB_I2C_RESOURCE</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_extended_address.md">PEP_ACPI_EXTENDED_ADDRESS</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_interrupt_resource.md">PEP_ACPI_INTERRUPT_RESOURCE</a>



<a href="..\pepfx\ne-pepfx-_pep_acpi_resource_type.md">PEP_ACPI_RESOURCE_TYPE</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_io_memory_resource.md">PEP_ACPI_IO_MEMORY_RESOURCE</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_spb_uart_resource.md">PEP_ACPI_SPB_UART_RESOURCE</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_spb_spi_resource.md">PEP_ACPI_SPB_SPI_RESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_RESOURCE union%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>