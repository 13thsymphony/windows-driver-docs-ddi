---
UID: NS.PEPFX._PEP_ACPI_INTERRUPT_RESOURCE
title: _PEP_ACPI_INTERRUPT_RESOURCE
author: windows-driver-content
description: The PEP_ACPI_INTERRUPT_RESOURCE structure describes an ACPI interrupt resource.
old-location: kernel\pep_acpi_interrupt_resource.htm
old-project: kernel
ms.assetid: B440AB0E-72CC-40F1-B77E-C12C84124737
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PEP_ACPI_INTERRUPT_RESOURCE, PEP_ACPI_INTERRUPT_RESOURCE, *PPEP_ACPI_INTERRUPT_RESOURCE
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
req.alt-api: PEP_ACPI_INTERRUPT_RESOURCE
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
---

# _PEP_ACPI_INTERRUPT_RESOURCE structure



## -description
The <b>PEP_ACPI_INTERRUPT_RESOURCE</b> structure describes an ACPI interrupt resource.


## -syntax

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


## -struct-fields

### -field Type

A <a href="kernel.pep_acpi_resource_type">PEP_ACPI_RESOURCE_TYPE</a> enumeration value describing this resource.

### -field InterruptType

A <a href="kernel.kinterrupt_mode">KINTERRUPT_MODE</a> enumeration value that identifies the interrupt type.

### -field InterruptPolarity

A <a href="kernel.kinterrupt_polarity">KINTERRUPT_POLARITY</a> enumeration value that identifies how a device signals an interrupt request on an interrupt line.

### -field Flags

A <a href="kernel.pep_acpi_resource_flags">PEP_ACPI_RESOURCE_FLAGS</a> structure that describes the capabilities of this ACPI resource.

### -field Count

The count of items in the <b>Pins</b> array.

### -field Pins

A list of pin numbers on the resource that are described by this descriptor. 

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
<a href="kernel.pep_acpi_resource_type">PEP_ACPI_RESOURCE_TYPE</a>
</dt>
<dt>
<a href="kernel.kinterrupt_mode">KINTERRUPT_MODE</a>
</dt>
<dt>
<a href="kernel.kinterrupt_polarity">KINTERRUPT_POLARITY</a>
</dt>
<dt>
<a href="kernel.pep_acpi_resource_flags">PEP_ACPI_RESOURCE_FLAGS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INTERRUPT_RESOURCE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
