---
UID: NS:wdm._PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
title: "_PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK"
author: windows-driver-content
description: The PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) uncorrectable error mask register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_uncorrectable_error_mask.htm
old-project: PCI
ms.assetid: 0dfc6e49-5556-4163-abef-b00a26a7a2ad
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, PCI.pci_express_uncorrectable_error_mask, PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK union [Buses], PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK union pointer [Buses], _PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, pci_struct_309db853-f6d7-4f88-9a73-861d63a1e927.xml, wdm/PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, wdm/PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h, Miniport.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
product: Windows
targetos: Windows
req.typenames: PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure
The PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) uncorrectable error mask register of a PCIe advanced error reporting capability structure.

## Syntax
````
typedef union _PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK {
  struct {
    ULONG Undefined  :1;
    ULONG Reserved1  :3;
    ULONG DataLinkProtocolError  :1;
    ULONG SurpriseDownError  :1;
    ULONG Reserved2  :6;
    ULONG PoisonedTLP  :1;
    ULONG FlowControlProtocolError  :1;
    ULONG CompletionTimeout  :1;
    ULONG CompleterAbort  :1;
    ULONG UnexpectedCompletion  :1;
    ULONG ReceiverOverflow  :1;
    ULONG MalformedTLP  :1;
    ULONG ECRCError  :1;
    ULONG UnsupportedRequestError  :1;
    ULONG Reserved3  :11;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_MASK;
````

## Members


`DUMMYSTRUCTNAME`



`AsULONG`

A ULONG representation of the contents of the PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure.

## Remarks
The PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Ntddk.h, Wdm.h, Miniport.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>