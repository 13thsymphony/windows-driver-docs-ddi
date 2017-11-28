---
UID: NS.wdm._PCI_CAPABILITIES_HEADER
title: PCI_CAPABILITIES_HEADER
author: windows-driver-content
description: The PCI_CAPABILITIES_HEADER structure defines a header that is present in every PCI capability structure.
old-location: pci\pci_capabilities_header.htm
old-project: PCI
ms.assetid: 6a2ee9be-03bc-436d-91c7-f00222911b19
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PCI_CAPABILITIES_HEADER, PCI_CAPABILITIES_HEADER, *PPCI_CAPABILITIES_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCI_CAPABILITIES_HEADER
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

# PCI_CAPABILITIES_HEADER structure



## -description
<p>The PCI_CAPABILITIES_HEADER structure defines a header that is present in every PCI capability structure. </p>


## -syntax

````
typedef struct _PCI_CAPABILITIES_HEADER {
  UCHAR CapabilityID;
  UCHAR Next;
} PCI_CAPABILITIES_HEADER, *PPCI_CAPABILITIES_HEADER;
````


## -struct-fields
<dl>

### -field <b>CapabilityID</b>

<dd>
<p>Contains an 8-bit integer that indicates the capability ID. The capability ID identifies the type of capability structure that follows this header. The <b>CapabilityID</b> member must have one of the following values:</p>
<table>
<tr>
<th>Capability ID</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_POWER_MANAGEMENT</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines a PCI power management interface. For more information about this kind of capability, see the <i>PCI Power Management Interface Specificatio</i>n. </p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_AGP</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines the Accelerated Graphics Port (AGP) supported by the device. For more information about this kind of capability, see the <i>Accelerated Graphics Port Interface Specification.</i></p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_VPD</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines Vital Product Data (VPD) features of the device.</p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_SLOT_ID</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines external expansion capabilities of a bridge device. For more information about this kind of capability, see the <i>PCI to PCI Bridge Architecture Specificatio</i>n. </p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_MSI</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines a <i>PCI device</i> that can do message signaled interrupt (MSI) delivery. For more information about the MSI capability, see the <i>PCI Local Bus Specification</i>. </p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_CPCI_HOTSWAP</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines a standard interface to control and sense status. Devices that supports hot swap insertion and extraction in a CompactPCI system require this kind of interface. For more information about control and sense status in CompactPCI systems, see the <i>CompactPCI Hot Swap Specification</i>. </p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_PCIX</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines the devices PCI-X features. For more information about PCI-X, see the <i>PCI-X Addendum to the PCI Local Bus Specification</i>.</p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_HYPERTRANSPORT</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines control and status for devices that implement hyper transport (HT) technology links. For more information about HT technology, refer to the <i>HyperTransport I/O Link Specification</i>. </p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_VENDOR_SPECIFIC</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines vendor specific information. For more information about how to use the capability mechanism to communicate vendor-specific information, see the <i>PCI Local Bus Specification</i>. </p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_DEBUG_PORT</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header describes a debug port</p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_CPCI_RES_CTRL</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header describes CompactPCI central resource control. For more information about this kind of control see the <i>PICMG 2.13 Specification</i>. </p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_SHPC</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines the features of a device that conforms to the standard hot-plug controller model.</p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_P2P_SSID</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines the subsystem ID capability.</p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_AGP_TARGET</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines the Accelerated Graphics Port (AGP) 8x capability. </p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_SECURE</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header describes a secure device</p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_PCI_EXPRESS</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines a device that supports PCI express.</p>
</td>
</tr>
<tr>
<td>
<p>PCI_CAPABILITY_ID_MSIX</p>
</td>
<td>
<p>Indicates that the capability structure that follows the header defines an optional extension to the basic MSI functionality.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>Next</b>

<dd>
<p>Contains an offset into the PCI configuration space that indicates the location of the next item in the capability list. If there are no additional items in the list, this member will contain zero. </p>
</dd>
</dl>

## -remarks
<p>All PCI Capability structures have the header described by PCI_CAPABILITIES_HEADER. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537581">PCI_PMC</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537583">PCI_PMCSR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537587">PCI_PMCSR_BSE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_CAPABILITIES_HEADER structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
