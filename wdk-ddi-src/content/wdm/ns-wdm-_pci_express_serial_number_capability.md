---
UID: NS:wdm._PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
title: _PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
author: windows-driver-content
description: The PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure describes a serial number for a PCI Express (PCIe) device.
old-location: pci\pci_express_serial_number_capability.htm
old-project: PCI
ms.assetid: ad8b8740-35bc-4aa4-a190-00d1a78e447a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY, *PPCI_EXPRESS_SERIAL_NUMBER_CAPABILITY, PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: *PPCI_EXPRESS_SERIAL_NUMBER_CAPABILITY, PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure



## -description
The PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure describes a serial number for a PCI Express (PCIe) device.



## -syntax

````
typedef struct _PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY {
  PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER Header;
  ULONG                                  LowSerialNumber;
  ULONG                                  HighSerialNumber;
} PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY, *PPCI_EXPRESS_SERIAL_NUMBER_CAPABILITY;
````


## -struct-fields

### -field Header

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537466">PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER</a> structure that describes the header for this structure.


### -field LowSerialNumber

The lower 32 bits of the serial number.


### -field HighSerialNumber

The upper 32 bits of the serial number.


## -remarks
The PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure is available in Windows Server 2008 and later versions of Windows.

The PCIe device serial number capability is an optional extended capability that can be implemented by any PCIe device. The device serial number is a 64-bit value that is unique for a given PCIe device.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537466">PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

