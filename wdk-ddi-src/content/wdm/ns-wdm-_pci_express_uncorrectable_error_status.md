---
UID: NS:wdm._PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
title: "_PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS"
author: windows-driver-content
description: The PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) uncorrectable error status register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_uncorrectable_error_status.htm
old-project: PCI
ms.assetid: 9d7dcdee-052a-4082-a337-be3a35c5eef9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, PCI.pci_express_uncorrectable_error_status, PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS union [Buses], PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS union pointer [Buses], _PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, pci_struct_9341a010-06c8-46ee-931f-2a67756c12d2.xml, wdm/PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, wdm/PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS"
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
-	PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
product: Windows
targetos: Windows
req.typenames: PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure
The PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) uncorrectable error status register of a PCIe advanced error reporting capability structure.

## Syntax
````
typedef union _PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS {
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
} PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS;
````

## Members


`AsULONG`

A ULONG representation of the contents of the PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure.

`DUMMYSTRUCTNAME`



## Remarks
The PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Ntddk.h, Wdm.h, Miniport.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS union%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>