---
UID: NS.WDM.PPCI_X_CAPABILITY
title: PPCI_X_CAPABILITY
author: windows-driver-content
description: The PCI_X_CAPABILITY structure reports the contents of the command and status registers of a device that is compliant with the PCI-X Addendum to the PCI Local Bus Specification.
old-location: pci\pci_x_capability.htm
old-project: PCI
ms.assetid: b30ccf86-ae6d-484a-a3f2-8b38df26e995
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PPCI_X_CAPABILITY, PCI_X_CAPABILITY, *PPCI_X_CAPABILITY
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
req.alt-api: PCI_X_CAPABILITY
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

# PPCI_X_CAPABILITY structure



## -description
The PCI_X_CAPABILITY structure reports the contents of the command and status registers of a device that is compliant with the <i>PCI-X Addendum to the PCI Local Bus Specification.</i>


## -syntax

````
typedef struct {
  PCI_CAPABILITIES_HEADER Header;
  union {
    struct {
      USHORT DataParityErrorRecoveryEnable  :1;
      USHORT EnableRelaxedOrdering  :1;
      USHORT MaxMemoryReadByteCount  :2;
      USHORT MaxOutstandingSplitTransactions  :3;
      USHORT Reserved  :9;
    } bits;
    USHORT AsUSHORT;
  } Command;
  union {
    struct {
      ULONG FunctionNumber;
      ULONG DeviceNumber;
      ULONG BusNumber;
      ULONG Device64Bit;
      ULONG Capable133MHz;
      ULONG SplitCompletionDiscarded;
      ULONG UnexpectedSplitCompletion;
      ULONG DeviceComplexity;
      ULONG DesignedMaxMemoryReadByteCount;
      ULONG DesignedMaxOutstandingSplitTransactions;
      ULONG DesignedMaxCumulativeReadSize;
      ULONG ReceivedSplitCompletionErrorMessage;
      ULONG CapablePCIX266;
      ULONG CapablePCIX533;
    } bits;
    ULONG  AsULONG;
  } Status;
} PCI_X_CAPABILITY, *PPCI_X_CAPABILITY;
````


## -struct-fields

### -field Header

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537454">PCI_CAPABILITIES_HEADER</a> that identifies the capability and provides a link to the next capability description. 

### -field Command


### -field bits


### -field DataParityErrorRecoveryEnable

Indicates that the data parity error recovery bit is set in the device's command register, and the device will attempt to recover from data parity errors. For more information about the significance of the value in the parity error recovery bit, see the <i>PCI Local Bus Specification</i>. 

### -field EnableRelaxedOrdering

Indicates the enable relaxed ordering bit is set in the device's command register. This leaves the device free to adopt a more relaxed transaction ordering policy. For more information about how this bit effects transaction ordering, see the <i>PCI Local Bus Specification</i>. 

### -field MaxMemoryReadByteCount

Reports the maximum byte count, recorded in the command register, that the device uses when initiating a burst memory read command. For more information about how this bit effects read commands, see the <i>PCI Local Bus Specification</i>. 

### -field MaxOutstandingSplitTransactions

Reports the maximum number of split transactions, recorded in the command register, that the device can initiate asynchronously. For more information about how this value effects split transactions, see the <i>PCI Local Bus Specification</i>. 

### -field Reserved

Reserved. 
</dd>
</dl>

### -field AsUSHORT

Reports the data in the device's command register in the form of a unsigned long integer.
</dd>
</dl>

### -field Status


### -field bits


### -field FunctionNumber

Indicates the value in the function number field of an address of a type 0 configuration transaction. For more information about the meaning of this number, see the <i>PCI Local Bus Specification</i>. 

### -field DeviceNumber

Indicates the value in the device number field of the address of a type 0 configuration transaction. For more information about the meaning of this number, see the <i>PCI Local Bus Specification</i>. 

### -field BusNumber

Indicates the number of the bus segment on which the device is located. For more information about the meaning of this number, see the <i>PCI Local Bus Specification</i>. 

### -field Device64Bit

Indicates when 1 that the bus is 64 bits wide. When 0 the bus is 32 bits wide. For more information about the meaning of the status register's device 64 bit, see the <i>PCI Local Bus Specification</i>. 

### -field Capable133MHz

Indicates when 1 that the device's maximum operating frequency is 133 MHz. Indicates when 0 that the device's maximum operating frequency is 66 MHz. For more information about the meaning of status register's capable 133 Mhz bit, see the <i>PCI Local Bus Specification</i>. 

### -field SplitCompletionDiscarded

Indicates when 1 that the device discarded a split completion transaction because the requester rejected it. A value of 0 indicates that the device has not discarded any split completion transactions since the status register's split completion discarded bit was last cleared. For more information about the status register's split completion discarded bit, see the <i>PCI Local Bus Specification</i>. 

### -field UnexpectedSplitCompletion

Indicates when 1 that the device has received a split completion transaction with the device's requester ID. Indicates when 0 that the device has not received this kind of transaction. For more information about the meaning of the status register's unexpected split completion bit, see the <i>PCI Local Bus Specification</i>. 

### -field DeviceComplexity

Indicates when 1 that the device is a bridge device. When 0 the device is not a bridge device. For more information about the meaning of the status register's device complexity bit, see the <i>PCI Local Bus Specification</i>. 

### -field DesignedMaxMemoryReadByteCount

Reports the maximum byte count, defined in the status register, that the device uses when it initiates a read sequence. For more information about the meaning of this value, see the <i>PCI Local Bus Specification</i>. 

### -field DesignedMaxOutstandingSplitTransactions

Reports the maximum number of split transactions, defined in the status register, that the device can permit at any one time. For more information about the meaning of this value, see the <i>PCI Local Bus Specification</i>. 

### -field DesignedMaxCumulativeReadSize

Reports the maximum number of burst memory read transactions, defined in the status register, that the device allows at any one time. For more information about this value, see the <i>PCI Local Bus Specification</i>. 

### -field ReceivedSplitCompletionErrorMessage

Indicates when 1 that the device has received a split completion error message. Indicates when 0 that the device has not received a split completion error message. 
</dd>
</dl>

### -field AsULONG

Reports the data in the device's status register in the form of a unsigned long integer.
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537454">PCI_CAPABILITIES_HEADER</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_X_CAPABILITY structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
