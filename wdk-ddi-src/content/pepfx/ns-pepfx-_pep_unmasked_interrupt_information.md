---
UID: NS.PEPFX._PEP_UNMASKED_INTERRUPT_INFORMATION
title: _PEP_UNMASKED_INTERRUPT_INFORMATION
author: windows-driver-content
description: The PEP_UNMASKED_INTERRUPT_INFORMATION structure contains information about an interrupt source.
old-location: kernel\pep_unmasked_interrupt_information.htm
old-project: kernel
ms.assetid: 1DD9A0A2-7D19-419A-8653-C16FDB28299E
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PEP_UNMASKED_INTERRUPT_INFORMATION, *PPEP_UNMASKED_INTERRUPT_INFORMATION, PEP_UNMASKED_INTERRUPT_INFORMATION
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
req.alt-api: PEP_UNMASKED_INTERRUPT_INFORMATION
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

# _PEP_UNMASKED_INTERRUPT_INFORMATION structure



## -description
The <b>PEP_UNMASKED_INTERRUPT_INFORMATION</b> structure contains information about an interrupt source.


## -syntax

````
typedef struct _PEP_UNMASKED_INTERRUPT_INFORMATION {
  USHORT                       Version;
  USHORT                       Size;
  PEP_UNMASKED_INTERRUPT_FLAGS Flags;
  KINTERRUPT_MODE              Mode;
  KINTERRUPT_POLARITY          Polarity;
  ULONG                        Gsiv;
  USHORT                       PinNumber;
  PEPHANDLE                    DeviceHandle;
} PEP_UNMASKED_INTERRUPT_INFORMATION, *PPEP_UNMASKED_INTERRUPT_INFORMATION;
````


## -struct-fields

### -field Version

The version of this structure.

### -field Size

The size, in bytes, of this structure.

### -field Flags

A <a href="kernel.pep_unmasked_interrupt_flags">PEP_UNMASKED_INTERRUPT_FLAGS</a> union that indicates whether the interrupt is a primary or secondary interrupt. For more information, see <a href="https://msdn.microsoft.com/731B0E36-4480-4B69-931E-1F7B40B18911">Primary and Secondary Interrupts</a>.

### -field Mode

A <a href="kernel.kinterrupt_mode">KINTERRUPT_MODE</a> enumeration value. This member indicates whether the interrupt is edge-triggered or level-triggered.

### -field Polarity

A <a href="kernel.kinterrupt_polarity">KINTERRUPT_POLARITY</a> enumeration value. This member indicates which edge or level of the interrupt signal triggers the interrupt.

### -field Gsiv

The global system interrupt vector (GSIV) number that identifies this interrupt. The ACPI firmware assigns GSIV numbers to all primary interrupt lines. For secondary (GPIO) interrupt lines, the GSIV number is dynamically assigned by the operating system.

### -field PinNumber

For secondary interrupt sources, this member identifies the number of the pin on the general-purpose I/O (GPIO) controller that is connected to the interrupt signal line from the interrupting device. For primary interrupt sources, this member is undefined.
If a GPIO controller has N GPIO pins, the pins are numbered 0 to N–1. One or more of these GPIO pins might be configured as interrupt inputs.

### -field DeviceHandle

For secondary interrupt sources, this member contains the PEP device handle for the GPIO controller that is the source for this interrupt. For primary interrupt sources, this field is undefined.

## -remarks
This structure is used by the <a href="kernel.enumerateinterruptsource">EnumerateInterruptSource</a> callback routine.

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
<a href="kernel.enumerateinterruptsource">EnumerateInterruptSource</a>
</dt>
<dt>
<a href="kernel.kinterrupt_mode">KINTERRUPT_MODE</a>
</dt>
<dt>
<a href="kernel.kinterrupt_polarity">KINTERRUPT_POLARITY</a>
</dt>
<dt>
<a href="kernel.pep_unmasked_interrupt_flags">PEP_UNMASKED_INTERRUPT_FLAGS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_UNMASKED_INTERRUPT_INFORMATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
