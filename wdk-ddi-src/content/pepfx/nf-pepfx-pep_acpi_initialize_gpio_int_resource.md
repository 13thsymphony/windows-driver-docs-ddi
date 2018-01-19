---
UID : NF:pepfx.PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE
title : PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function
author : windows-driver-content
description : The PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_GPIO_RESOURCE structure.
old-location : kernel\pep_acpi_initialize_gpio_int_resource.htm
old-project : kernel
ms.assetid : EF8E3D1D-9C87-4083-A022-FD888D370B20
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : pepfx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE
req.alt-loc : pepfx.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PPEP_WORK_TYPE, PEP_WORK_TYPE"
---


# PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function
The <b>PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx-_pep_acpi_gpio_resource.md">PEP_ACPI_GPIO_RESOURCE</a> structure.

## Syntax

````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE(
  _In_  KINTERRUPT_MODE      InterruptType,
  _In_  KINTERRUPT_POLARITY  LevelType,
  _In_  BOOLEAN              Shareable,
  _In_  BOOLEAN              CanWake,
  _In_  GPIO_PIN_CONFIG_TYPE PinConfig,
  _In_  USHORT               DebounceTimeout,
  _In_  UCHAR                ResourceSourceIndex,
  _In_  PUNICODE_STRING      ResourceSourceName,
  _In_  BOOLEAN              ResourceUsage,
  _In_  PUCHAR               VendorData,
  _In_  USHORT               VendorDataLength,
  _In_  PUSHORT              PinTable,
  _In_  UCHAR                PinCount,
  _Out_ PPEP_ACPI_RESOURCE   Resource
);
````

## Parameters

`InterruptType`

A <a href="..\wdm\ne-wdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a> enumeration value that identifies the interrupt type.

`LevelType`

A <a href="..\wdm\ne-wdm-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a> enumeration value that identifies how a device signals an interrupt request on an interrupt line.

`Shareable`

Indicates if the device can be shared.

`CanWake`

Indicates if the device can be woken from a low-power state.

`PinConfig`

A <a href="..\pepfx\ne-pepfx-_gpio_pin_config_type.md">GPIO_PIN_CONFIG_TYPE</a> enumeration value that identifies the GPIO pin configuration type.

`DebounceTimeout`

Specifies the hardware debounce wait time, in hundredths of milliseconds.

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
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_acpi_gpio_resource.md">PEP_ACPI_GPIO_RESOURCE</a>
</dt>
<dt>
<a href="..\pepfx\ne-pepfx-_gpio_pin_config_type.md">GPIO_PIN_CONFIG_TYPE</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>