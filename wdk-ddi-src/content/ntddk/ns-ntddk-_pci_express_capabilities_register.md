---
UID: NS.NTDDK._PCI_EXPRESS_CAPABILITIES_REGISTER
title: _PCI_EXPRESS_CAPABILITIES_REGISTER
author: windows-driver-content
description: The PCI_EXPRESS_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) capabilities register of a PCIe capability structure.
old-location: pci\pci_express_capabilities_register.htm
old-project: PCI
ms.assetid: aae9218e-e52b-4a72-9d96-d648ff6d2f5d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PCI_EXPRESS_CAPABILITIES_REGISTER, PCI_EXPRESS_CAPABILITIES_REGISTER, *PPCI_EXPRESS_CAPABILITIES_REGISTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCI_EXPRESS_CAPABILITIES_REGISTER
req.alt-loc: ntddk.h
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

# _PCI_EXPRESS_CAPABILITIES_REGISTER structure



## -description
The PCI_EXPRESS_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) capabilities register of a PCIe capability structure.



## -syntax

````
typedef union _PCI_EXPRESS_CAPABILITIES_REGISTER {
  struct {
    USHORT CapabilityVersion  :4;
    USHORT DeviceType  :4;
    USHORT SlotImplemented  :1;
    USHORT InterruptMessageNumber  :5;
    USHORT Rsvd  :2;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_CAPABILITIES_REGISTER, *PPCI_EXPRESS_CAPABILITIES_REGISTER;
````


## -struct-fields

### -field CapabilityVersion

The version number of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure that contains the PCI_EXPRESS_CAPABILITIES_REGISTER structure.


### -field DeviceType

The type of PCIe logical device. Possible values are:




### -field PciExpressEndpoint

A PCIe endpoint device.


### -field PciExpressLegacyEndpoint

A legacy PCIe endpoint device.


### -field PciExpressRootPort

A root port of a PCIe root complex.


### -field PciExpressUpstreamSwitchPort

An upstream port of a PCIe switch.


### -field PciExpressDownstreamSwitchPort

A downstream port of a PCIe switch.


### -field PciExpressToPciXBridge

A PCIe-to-PCI or PCI-X bridge.


### -field PciXToExpressBridge

A PCI- or PCI-X-to PCIe bridge.


### -field PciExpressRootComplexIntegratedEndpoint

A PCIe endpoint device that is integrated into the root complex.


### -field PciExpressRootComplexEventCollector

A PCIe root complex event collector.

</dd>
</dl>

### -field SlotImplemented

A single bit that indicates that the PCIe link associated with this port is connected to a physical PCIe slot. This member is valid only if the <b>DeviceType</b> member is set to <b>PciExpressRootPort</b> or <b>PciExpressDownstreamSwitchPort</b>.


### -field InterruptMessageNumber

The MSI or MSI-X vector that is used for interrupt messages that are generated in association with the status bits in either the slot status register or the root status register of the PCIe capability structure.


### -field Rsvd

Reserved.


### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_CAPABILITIES_REGISTER structure.


## -remarks
The PCI_EXPRESS_CAPABILITIES_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_CAPABILITIES_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_CAPABILITIES_REGISTER union%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

