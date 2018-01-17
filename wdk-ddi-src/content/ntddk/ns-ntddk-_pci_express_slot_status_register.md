---
UID: NS:ntddk._PCI_EXPRESS_SLOT_STATUS_REGISTER
title: _PCI_EXPRESS_SLOT_STATUS_REGISTER
author: windows-driver-content
description: The PCI_EXPRESS_SLOT_STATUS_REGISTER structure describes a PCI Express (PCIe) slot status register of a PCIe capability structure.
old-location: pci\pci_express_slot_status_register.htm
old-project: PCI
ms.assetid: 1012abf2-a73b-49d9-8017-b0b1a1c7fbcd
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _PCI_EXPRESS_SLOT_STATUS_REGISTER, PCI_EXPRESS_SLOT_STATUS_REGISTER, *PPCI_EXPRESS_SLOT_STATUS_REGISTER
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
req.alt-api: PCI_EXPRESS_SLOT_STATUS_REGISTER
req.alt-loc: ntddk.h
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
req.typenames: PCI_EXPRESS_SLOT_STATUS_REGISTER, *PPCI_EXPRESS_SLOT_STATUS_REGISTER
---

# _PCI_EXPRESS_SLOT_STATUS_REGISTER structure



## -description
The PCI_EXPRESS_SLOT_STATUS_REGISTER structure describes a PCI Express (PCIe) slot status register of a PCIe capability structure.



## -syntax

````
typedef union _PCI_EXPRESS_SLOT_STATUS_REGISTER {
  struct {
    USHORT AttentionButtonPressed  :1;
    USHORT PowerFaultDetected  :1;
    USHORT MRLSensorChanged  :1;
    USHORT PresenceDetectChanged  :1;
    USHORT CommandCompleted  :1;
    USHORT MRLSensorState  :1;
    USHORT PresenceDetectState  :1;
    USHORT ElectromechanicalLockEngaged  :1;
    USHORT DataLinkStateChanged  :1;
    USHORT Rsvd  :7;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_SLOT_STATUS_REGISTER, *PPCI_EXPRESS_SLOT_STATUS_REGISTER;
````


## -struct-fields

### -field AttentionButtonPressed

A single bit that indicates that the attention button for the slot is being pressed.


### -field PowerFaultDetected

A single bit that indicates that a power fault at the slot has been detected.


### -field MRLSensorChanged

A single bit that indicates that the state of the slot's manually operated retention latch (MRL) sensor has changed.


### -field PresenceDetectChanged

A single bit that indicates that the card presence detection state for the slot has changed.


### -field CommandCompleted

A single bit that indicates that a command has been completed by the slot's hot-plug controller.


### -field MRLSensorState

The slot's manually operated retention latch (MRL) sensor state. Possible values are:




### -field MRLClosed

The MRL is closed.


### -field MRLOpen

The MRL is open.

</dd>
</dl>

### -field PresenceDetectState

The slot's card presence detection state. Possible values are:




### -field SlotEmpty

The slot is empty.


### -field CardPresent

A card is present in the slot.

</dd>
</dl>

### -field ElectromechanicalLockEngaged

A single bit that indicates if the slot's electromechanical interlock is engaged.


### -field DataLinkStateChanged

A single bit that indicates that the data link layer active bit of the PCIe link status register of the PCIe capability structure has changed.


### -field Rsvd

Reserved.


### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_SLOT_STATUS_REGISTER structure.


## -remarks
The PCI_EXPRESS_SLOT_STATUS_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_SLOT_STATUS_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_SLOT_STATUS_REGISTER union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

