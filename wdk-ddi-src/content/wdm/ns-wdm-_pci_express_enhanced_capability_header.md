---
UID: NS.WDM._PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER
title: _PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER
author: windows-driver-content
description: The PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER structure describes the header for a PCI Express (PCIe) extended capability structure.
old-location: pci\pci_express_enhanced_capability_header.htm
old-project: PCI
ms.assetid: bc90a153-e6ff-4736-b625-1260a84bb157
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER, PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER, *PPCI_EXPRESS_ENHANCED_CAPABILITY_HEADER
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
req.alt-api: PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER
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

# _PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER structure



## -description
The PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER structure describes the header for a PCI Express (PCIe) extended capability structure.



## -syntax

````
typedef struct _PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER {
  USHORT CapabilityID;
  USHORT Version  :4;
  USHORT Next  :12;
} PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER, *PPCI_EXPRESS_ENHANCED_CAPABILITY_HEADER;
````


## -struct-fields

### -field CapabilityID

The extended capability identifier. Possible values are:




### -field PCI_EXPRESS_ADVANCED_ERROR_REPORTING_CAP_ID

Advanced error reporting capability


### -field PCI_EXPRESS_VIRTUAL_CHANNEL_CAP_ID

Virtual channel capability


### -field PCI_EXPRESS_DEVICE_SERIAL_NUMBER_CAP_ID

Device serial number capability


### -field PCI_EXPRESS_POWER_BUDGETING_CAP_ID

Power budgeting capability


### -field PCI_EXPRESS_RC_LINK_DECLARATION_CAP_ID

Root complex link declaration capability


### -field PCI_EXPRESS_RC_INTERNAL_LINK_CONTROL_CAP_ID

Root complex internal link control capability


### -field PCI_EXPRESS_RC_EVENT_COLLECTOR_ENDPOINT_ASSOCIATION_CAP_ID

Root complex event collector endpoint association capability


### -field PCI_EXPRESS_MFVC_CAP_ID

Multi-function virtual channel capability


### -field PCI_EXPRESS_VC_AND_MFVC_CAP_ID

Virtual channel and multi-function virtual channel capability


### -field PCI_EXPRESS_RCRB_HEADER_CAP_ID

Root complex register block header capability

</dd>
</dl>

### -field Version

The version of the extended capability structure. This member should be set to one for extended capability structures that are based on version 1.1 of the <i>PCIe Specification</i>.


### -field Next

The offset in PCIe device configuration space to the next PCIe capability structure in the linked list of capabilities. If this is the last PCIe capability structure in the list, this member is set to zero.


## -remarks
The PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER is included at the beginning of every extended capability structure. Microsoft defines structures for the advanced error reporting capability (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537458">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>) and the serial number capability (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537558">PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY</a>).


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537472">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537558">PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

