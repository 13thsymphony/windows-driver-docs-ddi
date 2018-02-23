---
UID: NF:pep_x.PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE
title: PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_GPIO_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_gpio_io_resource.htm
old-project: kernel
ms.assetid: D32E24E4-FAF4-401B-85FB-4D522C52093E
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: pepfx/PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE, PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE, kernel.pep_acpi_initialize_gpio_io_resource, PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE function [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE
product: Windows
targetos: Windows
req.typenames: "*PPEP_WORK_TYPE, PEP_WORK_TYPE"
---


# PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE function
The <b>PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx-_pep_acpi_gpio_resource.md">PEP_ACPI_GPIO_RESOURCE</a> structure.

## Syntax

````
__inline
VOID PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE(
  _In_  BOOLEAN                     Shareable,
  _In_  BOOLEAN                     CanWake,
  _In_  GPIO_PIN_CONFIG_TYPE        PinConfig,
  _In_  USHORT                      DebounceTimeout,
  _In_  USHORT                      DriveStrength,
  _In_  GPIO_PIN_IORESTRICTION_TYPE IoRestriction,
  _In_  UCHAR                       ResourceSourceIndex,
  _In_  PUNICODE_STRING             ResourceSourceName,
  _In_  BOOLEAN                     ResourceUsage,
  _In_  PUCHAR                      VendorData,
  _In_  USHORT                      VendorDataLength,
  _In_  PUSHORT                     PinTable,
  _In_  UCHAR                       PinCount,
  _Out_ PPEP_ACPI_RESOURCE          Resource
);
````

## Parameters

`Shareable`

Indicates if the device can be shared.

`CanWake`

Indicates if the device can be woken from a low-power state.

`PinConfig`

A <a href="..\pepfx\ne-pepfx-_gpio_pin_config_type.md">GPIO_PIN_CONFIG_TYPE</a> enumeration value that identifies the GPIO pin configuration type.

`DebounceTimeout`

Specifies the hardware debounce wait time, in hundredths of milliseconds.

`DriveStrength`



`IoRestriction`



`ResourceSourceIndex`

This parameter should always be zero.

`ResourceSourceName`

This parameter should always be "ResourceConsumer."

`ResourceUsage`

Indicates if this device is in use.

`VendorData`

A pointer to a raw data buffer containing vendor-defined byte data to be decoded by the OS driver.

`VendorDataLength`

The size of the buffer in the <i>VendorData</i> partameter.

`PinTable`

A list of pin numbers on the resource.

`PinCount`

The number of pins described by the <i>PinTable</i> parameter.

`Resource`

A pointer to the resource. The structure behind the pointer is of type <a href="..\pepfx\ns-pepfx-_pep_acpi_gpio_resource.md">PEP_ACPI_GPIO_RESOURCE</a>.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10.  |
| **Target Platform** | Windows |
| **Header** | pep_x.h (include Pep_x.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\pepfx\ne-pepfx-_gpio_pin_config_type.md">GPIO_PIN_CONFIG_TYPE</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_gpio_resource.md">PEP_ACPI_GPIO_RESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>