---
UID : NF:pepfx.PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE
title : PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function
author : windows-driver-content
description : The PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_I2C_RESOURCE structure.
old-location : kernel\pep_acpi_initialize_spb_i2c_resource.htm
old-project : kernel
ms.assetid : 5F1606D8-1E6F-494F-AE70-07A1EC1FEA47
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : pepfx/PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE, PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function [Kernel-Mode Driver Architecture], PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE, kernel.pep_acpi_initialize_spb_i2c_resource
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PEP_WORK_TYPE, *PPEP_WORK_TYPE
---


# PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function
The <b>PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_i2c_resource.md">PEP_ACPI_SPB_I2C_RESOURCE</a> structure.

## Syntax

````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE(
  _In_  USHORT             SlaveAddress,
  _In_  BOOLEAN            DeviceInitiated,
  _In_  ULONG              ConnectionSpeed,
  _In_  BOOLEAN            AddressingMode,
  _In_  PUNICODE_STRING    ResourceSource,
  _In_  UCHAR              ResourceSourceIndex,
  _In_  BOOLEAN            ResourceUsage,
  _In_  BOOLEAN            SharedMode,
  _In_  PCHAR              VendorData,
  _In_  USHORT             VendorDataLength,
  _Out_ PPEP_ACPI_RESOURCE Resource
);
````

## Parameters

`SlaveAddress`

The I2C bus address for this connection.

`DeviceInitiated`

If true, indicates that communication over this connection is initiated by the device.

`ConnectionSpeed`

The maximum speed, in hertz, supported by this connection.

`AddressingMode`

Indicates that this device is in addressing mode.

`ResourceSource`

The name of the serial bus controller device to which this
connection descriptor applies. The name can be a fully
qualified path, a relative path, or a simple name segment
that utilizes the namespace search rules.

`ResourceSourceIndex`

This parameter should always be set to zero.

`ResourceUsage`

Indicates if the resource is in use.

`SharedMode`

Indicates if the resource is shared.

`VendorData`

A pointer to optional data that is specific to the serial bus connection type.

`VendorDataLength`

The length of the buffer pointed to by the <i>VendorData</i> parameter.

`Resource`

A pointer to the resource. The structure behind the pointer is of type <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_i2c_resource.md">PEP_ACPI_SPB_I2C_RESOURCE</a>.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Target Platform** | Windows |
| **Header** | pepfx.h |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_acpi_spb_i2c_resource.md">PEP_ACPI_SPB_I2C_RESOURCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>