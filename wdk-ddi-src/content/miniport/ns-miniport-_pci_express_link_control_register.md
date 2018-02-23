---
UID: NS:miniport._PCI_EXPRESS_LINK_CONTROL_REGISTER
title: "_PCI_EXPRESS_LINK_CONTROL_REGISTER"
author: windows-driver-content
description: The PCI_EXPRESS_LINK_CONTROL_REGISTER structure describes a PCI Express (PCIe) link control register of a PCIe capability structure.
old-location: pci\pci_express_link_control_register.htm
old-project: PCI
ms.assetid: f4f8bd0d-fad7-4712-92ca-44d45969142d
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PPCI_EXPRESS_LINK_CONTROL_REGISTER, ntddk/PCI_EXPRESS_LINK_CONTROL_REGISTER, PCI_EXPRESS_LINK_CONTROL_REGISTER union [Buses], PCI_EXPRESS_LINK_CONTROL_REGISTER, pci_struct_0fc5be0f-aae8-4d59-a569-030eb593e927.xml, _PCI_EXPRESS_LINK_CONTROL_REGISTER, *PPCI_EXPRESS_LINK_CONTROL_REGISTER, ntddk/PPCI_EXPRESS_LINK_CONTROL_REGISTER, PCI.pci_express_link_control_register, PPCI_EXPRESS_LINK_CONTROL_REGISTER union pointer [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: miniport.h
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
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PCI_EXPRESS_LINK_CONTROL_REGISTER
product: Windows
targetos: Windows
req.typenames: "*PPCI_EXPRESS_LINK_CONTROL_REGISTER, PCI_EXPRESS_LINK_CONTROL_REGISTER"
---

# _PCI_EXPRESS_LINK_CONTROL_REGISTER structure
The PCI_EXPRESS_LINK_CONTROL_REGISTER structure describes a PCI Express (PCIe) link control register of a PCIe capability structure.

## Syntax
````
typedef union _PCI_EXPRESS_LINK_CONTROL_REGISTER {
  struct {
    USHORT ActiveStatePMControl  :2;
    USHORT Rsvd1  :1;
    USHORT ReadCompletionBoundary  :1;
    USHORT LinkDisable  :1;
    USHORT RetrainLink  :1;
    USHORT CommonClockConfig  :1;
    USHORT ExtendedSynch  :1;
    USHORT EnableClockPowerManagement  :1;
    USHORT Rsvd2  :7;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_LINK_CONTROL_REGISTER, *PPCI_EXPRESS_LINK_CONTROL_REGISTER;
````

## Members


`AsUSHORT`

A USHORT representation of the contents of the PCI_EXPRESS_LINK_CONTROL_REGISTER structure.

`DUMMYSTRUCTNAME`



## Remarks
The PCI_EXPRESS_LINK_CONTROL_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_LINK_CONTROL_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | miniport.h (include Ntddk.h, Miniport.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_LINK_CONTROL_REGISTER union%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>