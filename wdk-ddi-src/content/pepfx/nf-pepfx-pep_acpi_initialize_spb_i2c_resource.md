---
UID: NF.pepfx.PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE
title: PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_I2C_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_spb_i2c_resource.htm
old-project: kernel
ms.assetid: 5F1606D8-1E6F-494F-AE70-07A1EC1FEA47
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE
req.alt-loc: pepfx.h
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
---

# PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function



## -description
The <b>PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="kernel.pep_acpi_spb_i2c_resource">PEP_ACPI_SPB_I2C_RESOURCE</a> structure.


## -syntax

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


## -parameters

### -param SlaveAddress [in]

The I2C bus address for this connection.

### -param DeviceInitiated [in]

If true, indicates that communication over this connection is initiated by the device.

### -param ConnectionSpeed [in]

The maximum speed, in hertz, supported by this connection.

### -param AddressingMode [in]

Indicates that this device is in addressing mode.

### -param ResourceSource [in]

The name of the serial bus controller device to which this
connection descriptor applies. The name can be a fully
qualified path, a relative path, or a simple name segment
that utilizes the namespace search rules.

### -param ResourceSourceIndex [in]

This parameter should always be set to zero.

### -param ResourceUsage [in]

Indicates if the resource is in use.

### -param SharedMode [in]

Indicates if the resource is shared.

### -param VendorData [in]

A pointer to optional data that is specific to the serial bus connection type.

### -param VendorDataLength [in]

The length of the buffer pointed to by the <i>VendorData</i> parameter.

### -param Resource [out]

A pointer to the resource. The structure behind the pointer is of type <a href="kernel.pep_acpi_spb_i2c_resource">PEP_ACPI_SPB_I2C_RESOURCE</a>.

## -returns
This function does not return a value.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported starting with Windows 10.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_acpi_spb_i2c_resource">PEP_ACPI_SPB_I2C_RESOURCE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
