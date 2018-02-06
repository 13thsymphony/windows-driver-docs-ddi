---
UID: NS:wdm._PCI_EXPRESS_AER_CAPABILITY
title: "_PCI_EXPRESS_AER_CAPABILITY"
author: windows-driver-content
description: The PCI_EXPRESS_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure.
old-location: pci\pci_express_aer_capability.htm
old-project: PCI
ms.assetid: c389952b-2dc8-4c59-8543-633127a5a5f6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PCI_EXPRESS_AER_CAPABILITY, wdm/PCI_EXPRESS_AER_CAPABILITY, PPCI_EXPRESS_AER_CAPABILITY structure pointer [Buses], *PPCI_EXPRESS_AER_CAPABILITY, PCI_EXPRESS_AER_CAPABILITY structure [Buses], _PCI_EXPRESS_AER_CAPABILITY, PPCI_EXPRESS_AER_CAPABILITY, PCI.pci_express_aer_capability, wdm/PPCI_EXPRESS_AER_CAPABILITY, pci_struct_b9447d2e-502f-45f0-8851-ced834748798.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	PCI_EXPRESS_AER_CAPABILITY
product: Windows
targetos: Windows
req.typenames: "*PPCI_EXPRESS_AER_CAPABILITY, PCI_EXPRESS_AER_CAPABILITY"
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_AER_CAPABILITY structure
The PCI_EXPRESS_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure.

## Syntax
````
typedef struct _PCI_EXPRESS_AER_CAPABILITY {
  PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER       Header;
  PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS       UncorrectableErrorStatus;
  PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK         UncorrectableErrorMask;
  PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY     UncorrectableErrorSeverity;
  PCI_EXPRESS_CORRECTABLE_ERROR_STATUS         CorrectableErrorStatus;
  PCI_EXPRESS_CORRECTABLE_ERROR_MASK           CorrectableErrorMask;
  PCI_EXPRESS_AER_CAPABILITIES                 CapabilitiesAndControl;
  ULONG                                        HeaderLog[4];
  PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS   SecUncorrectableErrorStatus;
  PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK     SecUncorrectableErrorMask;
  PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY SecUncorrectableErrorSeverity;
  PCI_EXPRESS_SEC_AER_CAPABILITIES             SecCapabilitiesAndControl;
  ULONG                                        SecHeaderLog[4];
} PCI_EXPRESS_AER_CAPABILITY, *PPCI_EXPRESS_AER_CAPABILITY;
````

## Members


`CapabilitiesAndControl`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537456">PCI_EXPRESS_AER_CAPABILITIES</a> structure that describes the PCIe advanced error capabilities and control register of the PCIe AER capability structure.

`CorrectableErrorMask`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537567">PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK</a> structure that describes the PCIe uncorrectable error mask register of the PCIe AER capability structure.

`CorrectableErrorStatus`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537572">PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS</a> structure that describes the PCIe uncorrectable error status register of the PCIe AER capability structure.

`Header`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537466">PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER</a> structure that describes the header for this structure.

`HeaderLog`

An array of four 32-bit values that together contain the header for the transaction layer packet (TLP) that corresponds to a detected error.
<div class="alert"><b>Note</b>    Within each 32-bit value in the array, the bytes of the TLP are in big-endian byte order.</div><div> </div>

`SecCapabilitiesAndControl`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537478">PCI_EXPRESS_SEC_AER_CAPABILITIES</a> structure that describes the PCIe secondary error capabilities and control register of the PCIe AER capability structure.

`SecHeaderLog`

An array of four 32-bit values that together contain the header for the transaction on the secondary interface that generated an error.

`SecUncorrectableErrorMask`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537479">PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK</a> structure that describes the PCIe secondary uncorrectable error mask register of the PCIe AER capability structure.

`SecUncorrectableErrorSeverity`

A <a href="https://msdn.microsoft.com/b00aeced-037b-4bc5-97b7-96501262700f">PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERIT</a>Y structure that describes the PCIe secondary uncorrectable error severity register of the PCIe AER capability structure.

`SecUncorrectableErrorStatus`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537556">PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS</a> structure that describes the PCIe secondary uncorrectable error status register of the PCIe AER capability structure.

`UncorrectableErrorMask`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537567">PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK</a> structure that describes the PCIe uncorrectable error mask register of the PCIe AER capability structure.

`UncorrectableErrorSeverity`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537570">PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY</a> structure that describes the PCIe uncorrectable error severity register of the PCIe AER capability structure.

`UncorrectableErrorStatus`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537572">PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS</a> structure that describes the PCIe uncorrectable error status register of the PCIe AER capability structure.

## Remarks
The PCI_EXPRESS_AER_CAPABILITY structure is available in Windows Server 2008 and later versions of Windows.

PCIe bridge devices use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a> structure instead of the PCI_EXPRESS_AER_CAPABILITY structure to describe the PCIe advanced error reporting capability structure.

Root ports and root complex event collectors use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structure instead of the PCI_EXPRESS_AER_CAPABILITY structure to describe the PCIe advanced error reporting capability structure.

For additional information about the PCIe advanced error reporting capability structure, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=69486">PCI Express Specification</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Ntddk.h, Wdm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537570">PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537456">PCI_EXPRESS_AER_CAPABILITIES</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537462">PCI_EXPRESS_CORRECTABLE_ERROR_STATUS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537466">PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537567">PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537572">PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537461">PCI_EXPRESS_CORRECTABLE_ERROR_MASK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_AER_CAPABILITY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>