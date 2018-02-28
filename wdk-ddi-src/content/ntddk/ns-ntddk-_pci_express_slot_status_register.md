---
UID: NS:ntddk._PCI_EXPRESS_SLOT_STATUS_REGISTER
title: "_PCI_EXPRESS_SLOT_STATUS_REGISTER"
author: windows-driver-content
description: The PCI_EXPRESS_SLOT_STATUS_REGISTER structure describes a PCI Express (PCIe) slot status register of a PCIe capability structure.
old-location: pci\pci_express_slot_status_register.htm
old-project: PCI
ms.assetid: 1012abf2-a73b-49d9-8017-b0b1a1c7fbcd
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPCI_EXPRESS_SLOT_STATUS_REGISTER, PCI.pci_express_slot_status_register, PCI_EXPRESS_SLOT_STATUS_REGISTER, PCI_EXPRESS_SLOT_STATUS_REGISTER union [Buses], PPCI_EXPRESS_SLOT_STATUS_REGISTER, PPCI_EXPRESS_SLOT_STATUS_REGISTER union pointer [Buses], _PCI_EXPRESS_SLOT_STATUS_REGISTER, ntddk/PCI_EXPRESS_SLOT_STATUS_REGISTER, ntddk/PPCI_EXPRESS_SLOT_STATUS_REGISTER, pci_struct_2b218675-a1f4-4aec-a115-3046fac70492.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Miniport.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PCI_EXPRESS_SLOT_STATUS_REGISTER
product: Windows
targetos: Windows
req.typenames: PCI_EXPRESS_SLOT_STATUS_REGISTER, *PPCI_EXPRESS_SLOT_STATUS_REGISTER
---

# _PCI_EXPRESS_SLOT_STATUS_REGISTER structure
The PCI_EXPRESS_SLOT_STATUS_REGISTER structure describes a PCI Express (PCIe) slot status register of a PCIe capability structure.

## Syntax
````
typedef union _PCI_EXPRESS_SLOT_STATUS_REGISTER {
  struct {
    USHORT AttentionButtonPressed  :1;
    USHORT PowerFaultDetected  :1;
    USHORT MRLSensorChanged  :1;
    USHORT PresenceDetectChanged  :1;
    USHORT CommandCompleted  :1;
    USHORT MRLSensorState  :1;
    USHORT PresenceDetectState  :1;
    USHORT ElectromechanicalLockEngaged  :1;
    USHORT DataLinkStateChanged  :1;
    USHORT Rsvd  :7;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_SLOT_STATUS_REGISTER, *PPCI_EXPRESS_SLOT_STATUS_REGISTER;
````

## Members


`AsUSHORT`

A USHORT representation of the contents of the PCI_EXPRESS_SLOT_STATUS_REGISTER structure.

`DUMMYSTRUCTNAME`



## Remarks
The PCI_EXPRESS_SLOT_STATUS_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_SLOT_STATUS_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddk.h (include Ntddk.h, Miniport.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_SLOT_STATUS_REGISTER union%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>