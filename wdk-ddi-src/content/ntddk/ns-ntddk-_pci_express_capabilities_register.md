---
UID: NS:ntddk._PCI_EXPRESS_CAPABILITIES_REGISTER
title: "_PCI_EXPRESS_CAPABILITIES_REGISTER"
author: windows-driver-content
description: The PCI_EXPRESS_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) capabilities register of a PCIe capability structure.
old-location: pci\pci_express_capabilities_register.htm
old-project: PCI
ms.assetid: aae9218e-e52b-4a72-9d96-d648ff6d2f5d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: ntddk/PCI_EXPRESS_CAPABILITIES_REGISTER, *PPCI_EXPRESS_CAPABILITIES_REGISTER, PCI.pci_express_capabilities_register, PPCI_EXPRESS_CAPABILITIES_REGISTER union pointer [Buses], PCI_EXPRESS_CAPABILITIES_REGISTER, _PCI_EXPRESS_CAPABILITIES_REGISTER, pci_struct_86cc3b70-4de8-4479-b431-5f7f10d4a2f4.xml, PPCI_EXPRESS_CAPABILITIES_REGISTER, PCI_EXPRESS_CAPABILITIES_REGISTER union [Buses], ntddk/PPCI_EXPRESS_CAPABILITIES_REGISTER
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
-	PCI_EXPRESS_CAPABILITIES_REGISTER
product: Windows
targetos: Windows
req.typenames: "*PPCI_EXPRESS_CAPABILITIES_REGISTER, PCI_EXPRESS_CAPABILITIES_REGISTER"
---

# _PCI_EXPRESS_CAPABILITIES_REGISTER structure
The PCI_EXPRESS_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) capabilities register of a PCIe capability structure.

## Syntax
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

## Members


`AsUSHORT`

A USHORT representation of the contents of the PCI_EXPRESS_CAPABILITIES_REGISTER structure.

`DUMMYSTRUCTNAME`



## Remarks
The PCI_EXPRESS_CAPABILITIES_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_CAPABILITIES_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_CAPABILITIES_REGISTER union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>