---
UID: NS.wdm._PCI_EXPRESS_ROOT_ERROR_COMMAND
title: PCI_EXPRESS_ROOT_ERROR_COMMAND
author: windows-driver-content
description: The PCI_EXPRESS_ROOT_ERROR_COMMAND structure describes a PCI Express (PCIe) root error command register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_root_error_command.htm
old-project: PCI
ms.assetid: 659c0612-5623-4615-b9c5-6d2656097b89
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PCI_EXPRESS_ROOT_ERROR_COMMAND, PCI_EXPRESS_ROOT_ERROR_COMMAND, *PPCI_EXPRESS_ROOT_ERROR_COMMAND
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
req.alt-api: PCI_EXPRESS_ROOT_ERROR_COMMAND
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
req.iface: 
req.product: Windows 10 or later.
---

# PCI_EXPRESS_ROOT_ERROR_COMMAND structure



## -description
<p>The PCI_EXPRESS_ROOT_ERROR_COMMAND structure describes a PCI Express (PCIe) root error command register of a PCIe advanced error reporting capability structure.</p>


## -syntax

````
typedef union _PCI_EXPRESS_ROOT_ERROR_COMMAND {
  struct {
    ULONG CorrectableErrorReportingEnable  :1;
    ULONG NonFatalErrorReportingEnable  :1;
    ULONG FatalErrorReportingEnable  :1;
    ULONG Reserved  :29;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_ROOT_ERROR_COMMAND, *PPCI_EXPRESS_ROOT_ERROR_COMMAND;
````


## -struct-fields
<dl>

### -field CorrectableErrorReportingEnable

<dd>
<p>A single bit that indicates that interrupts are enabled for when a correctable error is reported by any of the devices in the hierarchy that are associated with this root port.</p>
</dd>

### -field NonFatalErrorReportingEnable

<dd>
<p>A single bit that indicates that interrupts are enabled for when a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port.</p>
</dd>

### -field FatalErrorReportingEnable

<dd>
<p>A single bit that indicates that interrupts are enabled for when a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved.</p>
</dd>

### -field AsULONG

<dd>
<p>A ULONG representation of the contents of the PCI_EXPRESS_ROOT_ERROR_COMMAND structure.</p>
</dd>
</dl>

## -remarks
<p>The PCI_EXPRESS_ROOT_ERROR_COMMAND structure is available in Windows Server 2008 and later versions of Windows.</p>

<p>A PCI_EXPRESS_ROOT_ERROR_COMMAND structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_ROOT_ERROR_COMMAND union%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
