---
UID: NS:ntddk._PCI_EXPRESS_CAPABILITY
title: "_PCI_EXPRESS_CAPABILITY"
author: windows-driver-content
description: The PCI_EXPRESS_CAPABILITY structure describes a PCI Express (PCIe) capability structure.
old-location: pci\pci_express_capability.htm
old-project: PCI
ms.assetid: f1faf319-95de-41f8-b32c-927ff4bb17ea
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "*PPCI_EXPRESS_CAPABILITY, ntddk/PPCI_EXPRESS_CAPABILITY, PCI_EXPRESS_CAPABILITY, PCI_EXPRESS_CAPABILITY structure [Buses], PPCI_EXPRESS_CAPABILITY structure pointer [Buses], pci_struct_9c629781-bcee-486d-bab3-5d5b7441ac72.xml, PPCI_EXPRESS_CAPABILITY, PCI.pci_express_capability, _PCI_EXPRESS_CAPABILITY, ntddk/PCI_EXPRESS_CAPABILITY"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PCI_EXPRESS_CAPABILITY
product: Windows
targetos: Windows
req.typenames: "*PPCI_EXPRESS_CAPABILITY, PCI_EXPRESS_CAPABILITY"
---

# _PCI_EXPRESS_CAPABILITY structure
The PCI_EXPRESS_CAPABILITY structure describes a PCI Express (PCIe) capability structure.

## Syntax
````
typedef struct _PCI_EXPRESS_CAPABILITY {
  PCI_CAPABILITIES_HEADER                  Header;
  PCI_EXPRESS_CAPABILITIES_REGISTER        ExpressCapabilities;
  PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER DeviceCapabilities;
  PCI_EXPRESS_DEVICE_CONTROL_REGISTER      DeviceControl;
  PCI_EXPRESS_DEVICE_STATUS_REGISTER       DeviceStatus;
  PCI_EXPRESS_LINK_CAPABILITIES_REGISTER   LinkCapabilities;
  PCI_EXPRESS_LINK_CONTROL_REGISTER        LinkControl;
  PCI_EXPRESS_LINK_STATUS_REGISTER         LinkStatus;
  PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER   SlotCapabilities;
  PCI_EXPRESS_SLOT_CONTROL_REGISTER        SlotControl;
  PCI_EXPRESS_SLOT_STATUS_REGISTER         SlotStatus;
  PCI_EXPRESS_ROOT_CONTROL_REGISTER        RootControl;
  PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER   RootCapabilities;
  PCI_EXPRESS_ROOT_STATUS_REGISTER         RootStatus;
} PCI_EXPRESS_CAPABILITY, *PPCI_EXPRESS_CAPABILITY;
````

## Members


`DeviceCapabilities`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537463">PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER</a> structure that describes the PCIe device capabilities register of the PCIe capability structure.

`DeviceCapabilities2`



`DeviceControl`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537464">PCI_EXPRESS_DEVICE_CONTROL_REGISTER</a> structure that describes the PCIe device control register of the PCIe capability structure.

`DeviceControl2`



`DeviceStatus`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537465">PCI_EXPRESS_DEVICE_STATUS_REGISTER</a> structure that describes the PCIe device status register of the PCIe capability structure.

`DeviceStatus2`



`ExpressCapabilities`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537459">PCI_EXPRESS_CAPABILITIES_REGISTER</a> structure that describes the PCIe capabilities register of the PCIe capability structure.

`Header`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537454">PCI_CAPABILITIES_HEADER</a> structure that describes the PCI capabilities header of the PCIe capability structure.

`LinkCapabilities`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537468">PCI_EXPRESS_LINK_CAPABILITIES_REGISTER</a> structure that describes the PCIe link capabilities register of the PCIe capability structure.

`LinkControl`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537469">PCI_EXPRESS_LINK_CONTROL_REGISTER</a> structure that describes the PCIe link control register of the PCIe capability structure.

`LinkStatus`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537470">PCI_EXPRESS_LINK_STATUS_REGISTER</a> structure that describes the PCIe link status register of the PCIe capability structure.

`RootCapabilities`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537473">PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER</a> structure that describes the PCIe root capabilities register of the PCIe capability structure.

`RootControl`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537474">PCI_EXPRESS_ROOT_CONTROL_REGISTER</a> structure that describes the PCIe root control register of the PCIe capability structure.

`RootStatus`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537477">PCI_EXPRESS_ROOT_STATUS_REGISTER</a> structure that describes the PCIe root status register of the PCIe capability structure.

`SlotCapabilities`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537560">PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER</a> structure that describes the PCIe slot capabilities register of the PCIe capability structure.

`SlotControl`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537562">PCI_EXPRESS_SLOT_CONTROL_REGISTER</a> structure that describes the PCIe slot control register of the PCIe capability structure.

`SlotStatus`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537564">PCI_EXPRESS_SLOT_STATUS_REGISTER</a> structure that describes the PCIe slot status register of the PCIe capability structure.

## Remarks
The PCI_EXPRESS_CAPABILITY structure is available in Windows Server 2008 and later versions of Windows.

For additional information about the PCIe capability structure, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=69486">PCI Express Specification</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537464">PCI_EXPRESS_DEVICE_CONTROL_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537562">PCI_EXPRESS_SLOT_CONTROL_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537477">PCI_EXPRESS_ROOT_STATUS_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537459">PCI_EXPRESS_CAPABILITIES_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537468">PCI_EXPRESS_LINK_CAPABILITIES_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537564">PCI_EXPRESS_SLOT_STATUS_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537465">PCI_EXPRESS_DEVICE_STATUS_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537473">PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537560">PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537474">PCI_EXPRESS_ROOT_CONTROL_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537470">PCI_EXPRESS_LINK_STATUS_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537463">PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537469">PCI_EXPRESS_LINK_CONTROL_REGISTER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537454">PCI_CAPABILITIES_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_CAPABILITY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>