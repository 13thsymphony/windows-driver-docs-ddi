---
UID: NS.WDM._PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
title: _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
author: windows-driver-content
description: The PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) correctable error status register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_correctable_error_status.htm
old-project: PCI
ms.assetid: 24d10f3a-5188-4dda-8e4e-1dc7ae2ddc88
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, *PPCI_CORRECTABLE_ERROR_STATUS
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
req.alt-api: PCI_EXPRESS_CORRECTABLE_ERROR_STATUS
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
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure



## -description
The PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) correctable error status register of a PCIe advanced error reporting capability structure.



## -syntax

````
typedef union _PCI_EXPRESS_CORRECTABLE_ERROR_STATUS {
  struct {
    ULONG ReceiverError  :1;
    ULONG Reserved1  :5;
    ULONG BadTLP  :1;
    ULONG BadDLLP  :1;
    ULONG ReplayNumRollover  :1;
    ULONG Reserved2  :3;
    ULONG ReplayTimerTimeout  :1;
    ULONG AdvisoryNonFatalError  :1;
    ULONG Reserved3  :18;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_CORRECTABLE_ERROR_STATUS, *PPCI_CORRECTABLE_ERROR_STATUS;
````


## -struct-fields

### -field ReceiverError

A single bit that indicates that a receiver error has occurred.


### -field Reserved1

Reserved.


### -field BadTLP

A single bit that indicates that a bad transaction layer packet (TLP) error has occurred.


### -field BadDLLP

A single bit that indicates that a bad data link layer packet (DLLP) error has occurred.


### -field ReplayNumRollover

A single bit that indicates that the counter that counts the number of times the retry buffer has been re-transmitted has rolled over.


### -field Reserved2

Reserved.


### -field ReplayTimerTimeout

A single bit that indicates that the replay timer has timed out.


### -field AdvisoryNonFatalError

A single bit that indicates that an advisory non-fatal error has occurred.


### -field Reserved3

Reserved.


### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure.


## -remarks
The PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Ntddk.h or Wdm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_CORRECTABLE_ERROR_STATUS union%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

