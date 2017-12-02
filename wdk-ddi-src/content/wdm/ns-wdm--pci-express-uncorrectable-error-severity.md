---
UID: NS.wdm._PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
title: PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
author: windows-driver-content
description: The PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure describes a PCI Express (PCIe) uncorrectable error severity register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_uncorrectable_error_severity.htm
old-project: PCI
ms.assetid: de2a908a-a032-4b61-963e-e5028ccdba11
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
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
req.alt-api: PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY
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

# PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure



## -description
<p>The PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure describes a PCI Express (PCIe) uncorrectable error severity register of a PCIe advanced error reporting capability structure.</p>


## -syntax

````
typedef union _PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY {
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
} PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY, *PPCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY;
````


## -struct-fields
<dl>

### -field Undefined

<dd>
<p>A single bit that contains an undefined value. In versions of the <i>PCIe Specification</i> prior to version 1.1, this bit indicates that a reported link training error is a fatal error.</p>
</dd>

### -field Reserved1

<dd>
<p>Reserved.</p>
</dd>

### -field DataLinkProtocolError

<dd>
<p>A single bit that indicates that a reported data link protocol error is a fatal error.</p>
</dd>

### -field SurpriseDownError

<dd>
<p>A single bit that indicates that a reported surprise down error is a fatal error.</p>
</dd>

### -field Reserved2

<dd>
<p>Reserved.</p>
</dd>

### -field PoisonedTLP

<dd>
<p>A single bit that indicates that a reported poisoned transaction layer packet (TLP) is a fatal error.</p>
</dd>

### -field FlowControlProtocolError

<dd>
<p>A single bit that indicates that a reported flow control protocol error is a fatal error.</p>
</dd>

### -field CompletionTimeout

<dd>
<p>A single bit that indicates that a reported completion timeout is a fatal error.</p>
</dd>

### -field CompleterAbort

<dd>
<p>A single bit that indicates that a reported completer abort is a fatal error.</p>
</dd>

### -field UnexpectedCompletion

<dd>
<p>A single bit that indicates that a reported unexpected completion is a fatal error.</p>
</dd>

### -field ReceiverOverflow

<dd>
<p>A single bit that indicates that a reported receiver overflow is a fatal error.</p>
</dd>

### -field MalformedTLP

<dd>
<p>A single bit that indicates that a reported malformed transaction layer packet (TLP) is a fatal error.</p>
</dd>

### -field ECRCError

<dd>
<p>A single bit that indicates that a reported end-to-end cyclic redundancy check (ECRC) error is a fatal error.</p>
</dd>

### -field UnsupportedRequestError

<dd>
<p>A single bit that indicates that a reported unsupported request error is a fatal error.</p>
</dd>

### -field Reserved3

<dd>
<p>Reserved.</p>
</dd>

### -field AsULONG

<dd>
<p>A ULONG representation of the contents of the PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure.</p>
</dd>
</dl>

## -remarks
<p>The PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure is available in Windows Server 2008 and later versions of Windows.</p>

<p>A PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY union%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
