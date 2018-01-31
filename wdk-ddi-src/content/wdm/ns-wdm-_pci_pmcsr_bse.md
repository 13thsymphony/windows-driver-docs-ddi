---
UID : NS:wdm._PCI_PMCSR_BSE
title : "_PCI_PMCSR_BSE"
author : windows-driver-content
description : The PCI_PMCSR_BSE structure is used to report the contents of the power management control status register for PCI bridge support extensions.
old-location : pci\pci_pmcsr_bse.htm
old-project : PCI
ms.assetid : f65116f6-0a61-4609-993b-d7b2eabf12b5
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : pci_struct_8ff8cc6c-91a4-4396-9d4c-8d99967a9417.xml, PPCI_PMCSR_BSE, PCI.pci_pmcsr_bse, PCI_PMCSR_BSE structure [Buses], wdm/PPCI_PMCSR_BSE, wdm/PCI_PMCSR_BSE, *PPCI_PMCSR_BSE, PPCI_PMCSR_BSE structure pointer [Buses], _PCI_PMCSR_BSE, PCI_PMCSR_BSE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL (see Remarks section)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPCI_PMCSR_BSE, PCI_PMCSR_BSE"
req.product : Windows 10 or later.
---

# _PCI_PMCSR_BSE structure
The PCI_PMCSR_BSE structure is used to report the contents of the power management control status register for PCI bridge support extensions.

## Syntax
````
typedef struct _PCI_PMCSR_BSE {
  UCHAR Rsvd1;
  UCHAR D3HotSupportsStopClock;
  UCHAR BusPowerClockControlEnabled;
} PCI_PMCSR_BSE, *PPCI_PMCSR_BSE;
````

## Members


`BusPowerClockControlEnabled`

Indicates, when 1, that the bus's power clock control mechanism is enabled. A value of 0 indicates that the bus power clock control mechanism is disabled.  For a detailed explanation of the meaning of this member, see the <i>PCI Power Management Specification</i>.

`D3HotSupportsStopClock`

Indicates how the power state of a secondary bus is affected when the primary bus transitions to a D3 power state. For a detailed explanation of the values in this member and how they affect the relationship between the primary and secondary buses, see the <i>PCI Power Management Specification</i>.

`Rsvd1`

Reserved.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537588">PCI_PM_CAPABILITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_PMCSR_BSE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>