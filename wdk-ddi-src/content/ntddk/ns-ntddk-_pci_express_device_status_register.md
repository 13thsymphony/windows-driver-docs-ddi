---
UID: NS:ntddk._PCI_EXPRESS_DEVICE_STATUS_REGISTER
title: _PCI_EXPRESS_DEVICE_STATUS_REGISTER
author: windows-driver-content
description: The PCI_EXPRESS_DEVICE_STATUS_REGISTER structure describes a PCI Express (PCIe) device status register of a PCIe capability structure.
old-location: pci\pci_express_device_status_register.htm
old-project: PCI
ms.assetid: a4c92364-59d4-442c-879b-fba770d8d612
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _PCI_EXPRESS_DEVICE_STATUS_REGISTER, *PPCI_EXPRESS_DEVICE_STATUS_REGISTER, PCI_EXPRESS_DEVICE_STATUS_REGISTER
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
req.alt-api: PCI_EXPRESS_DEVICE_STATUS_REGISTER
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
req.typenames: *PPCI_EXPRESS_DEVICE_STATUS_REGISTER, PCI_EXPRESS_DEVICE_STATUS_REGISTER
---

# _PCI_EXPRESS_DEVICE_STATUS_REGISTER structure



## -description
The PCI_EXPRESS_DEVICE_STATUS_REGISTER structure describes a PCI Express (PCIe) device status register of a PCIe capability structure.



## -syntax

````
typedef union _PCI_EXPRESS_DEVICE_STATUS_REGISTER {
  struct {
    USHORT CorrectableErrorDetected  :1;
    USHORT NonFatalErrorDetected  :1;
    USHORT FatalErrorDetected  :1;
    USHORT UnsupportedRequestDetected  :1;
    USHORT AuxPowerDetected  :1;
    USHORT TransactionsPending  :1;
    USHORT Rsvd  :10;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_DEVICE_STATUS_REGISTER, *PPCI_EXPRESS_DEVICE_STATUS_REGISTER;
````


## -struct-fields

### -field CorrectableErrorDetected

A single bit that indicates that a correctable error has been detected.


### -field NonFatalErrorDetected

A single bit that indicates that a non-fatal uncorrectable error has been detected.


### -field FatalErrorDetected

A single bit that indicates that a non-fatal uncorrectable error has been detected.


### -field UnsupportedRequestDetected

A single bit that indicates that an unsupported request has been detected.


### -field AuxPowerDetected

A single bit that indicates that AUX power has been detected.


### -field TransactionsPending

A single bit that indicates that the device has issued non-posted requests that have not been completed. The device clears this bit when all outstanding non-posted requests have completed or have been terminated by the completion timeout mechanism.


### -field Rsvd

Reserved.


### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_DEVICE_STATUS_REGISTER structure.


## -remarks
The <b>PCI_EXPRESS_DEVICE_STATUS_REGISTER</b> structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_DEVICE_STATUS_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_DEVICE_STATUS_REGISTER union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

