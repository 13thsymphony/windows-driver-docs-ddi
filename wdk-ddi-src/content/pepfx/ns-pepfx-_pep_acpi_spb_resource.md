---
UID: NS:pepfx._PEP_ACPI_SPB_RESOURCE
title: _PEP_ACPI_SPB_RESOURCE
author: windows-driver-content
description: The PEP_ACPI_SPB_RESOURCE structure describes an ACPI serial bus connection resource.
old-location: kernel\pep_acpi_spb_resource.htm
old-project: kernel
ms.assetid: D4C0009D-A9D0-4870-86C5-60DC9B5892BC
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PEP_ACPI_SPB_RESOURCE, PEP_ACPI_SPB_RESOURCE, *PPEP_ACPI_SPB_RESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_ACPI_SPB_RESOURCE
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
req.irql: PASSIVE_LEVEL
req.typenames: PEP_ACPI_SPB_RESOURCE, *PPEP_ACPI_SPB_RESOURCE
---

# _PEP_ACPI_SPB_RESOURCE structure



## -description
The <b>PEP_ACPI_SPB_RESOURCE</b> structure describes an ACPI serial bus connection resource.



## -syntax

````
typedef struct _PEP_ACPI_SPB_RESOURCE {
  PEP_ACPI_RESOURCE_TYPE  Type;
  PEP_ACPI_RESOURCE_FLAGS Flags;
  USHORT                  TypeSpecificFlags;
  UCHAR                   ResourceSourceIndex;
  PUNICODE_STRING         ResourceSourceName;
  PCHAR                   VendorData;
  USHORT                  VendorDataLength;
} PEP_ACPI_SPB_RESOURCE, *PPEP_ACPI_SPB_RESOURCE;
````


## -struct-fields

### -field Type

A <a href="..\pepfx\ne-pepfx-_pep_acpi_resource_type.md">PEP_ACPI_RESOURCE_TYPE</a> enumeration value describing this resource.


### -field Flags

A <a href="..\pepfx\ns-pepfx-_pep_acpi_resource_flags.md">PEP_ACPI_RESOURCE_FLAGS</a> structure that describes the capabilities of this ACPI resource.


### -field TypeSpecificFlags

Specifies the bit flags that are common to all serial bus connection types.

<table>
<tr>
<th>Bit(s)</th>
<th>Meaning</th>
</tr>
<tr>

### -field 0 - Slave mode

</td>
<td width="60%">
<b>0x0</b> - Indicates that communication over this connection is initiated by the controller.

<b>0x1</b> - Indicates that communication over this connection is initiated by the device.

</td>
</tr>
<tr>

### -field 1 - Consumer/producer mode

</td>
<td width="60%">
<b>0x0</b> - Indicates that this device produces and consumes this resource.

<b>0x1</b> - Indicates that this device consumes this resource.

</td>
</tr>
<tr>

### -field 2 to 7 - Reserved

</td>
<td width="60%">
These bits are reserved and must be set to zero.

</td>
</tr>
</table>
 


### -field ResourceSourceIndex


### -field ResourceSourceName

The name of the serial bus controller device to which this
connection descriptor applies. The name can be a fully
qualified path, a relative path, or a simple name segment
that utilizes the namespace search rules.


### -field VendorData

A pointer to optional data that is specific to the serial bus connection type.


### -field VendorDataLength

The length of the buffer pointed to by <b>VendorData</b>.


## -remarks
