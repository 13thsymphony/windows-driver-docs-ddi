---
UID: NS:ntddk._PCI_EXPRESS_DEVICE_CONTROL_REGISTER
title: _PCI_EXPRESS_DEVICE_CONTROL_REGISTER
author: windows-driver-content
description: The PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure describes a PCI Express (PCIe) device control register of a PCIe capability structure.
old-location: pci\pci_express_device_control_register.htm
old-project: PCI
ms.assetid: 888f88db-2149-4da2-acdb-4bf88a5362dd
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _PCI_EXPRESS_DEVICE_CONTROL_REGISTER, *PPCI_EXPRESS_DEVICE_CONTROL_REGISTER, PCI_EXPRESS_DEVICE_CONTROL_REGISTER
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
req.alt-api: PCI_EXPRESS_DEVICE_CONTROL_REGISTER
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
req.typenames: *PPCI_EXPRESS_DEVICE_CONTROL_REGISTER, PCI_EXPRESS_DEVICE_CONTROL_REGISTER
---

# _PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure



## -description
The PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure describes a PCI Express (PCIe) device control register of a PCIe capability structure.



## -syntax

````
typedef union _PCI_EXPRESS_DEVICE_CONTROL_REGISTER {
  struct {
    USHORT CorrectableErrorEnable  :1;
    USHORT NonFatalErrorEnable  :1;
    USHORT FatalErrorEnable  :1;
    USHORT UnsupportedRequestErrorEnable  :1;
    USHORT EnableRelaxedOrder  :1;
    USHORT MaxPayloadSize  :3;
    USHORT ExtendedTagEnable  :1;
    USHORT PhantomFunctionsEnable  :1;
    USHORT AuxPowerEnable  :1;
    USHORT NoSnoopEnable  :1;
    USHORT MaxReadRequestSize  :3;
    USHORT BridgeConfigRetryEnable  :1;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_DEVICE_CONTROL_REGISTER, *PPCI_EXPRESS_DEVICE_CONTROL_REGISTER;
````


## -struct-fields

### -field CorrectableErrorEnable

A single bit that indicates that reporting of correctable errors is enabled for the device.


### -field NonFatalErrorEnable

A single bit that indicates that reporting of non-fatal uncorrectable errors is enabled for the device.


### -field FatalErrorEnable

A single bit that indicates that reporting of non-fatal uncorrectable errors is enabled for the device.


### -field UnsupportedRequestErrorEnable

A single bit that indicates that reporting of unsupported requests is enabled for the device.


### -field EnableRelaxedOrder

A single bit that indicates that the device is permitted to set the relaxed ordering bit in the attributes field for any transactions that it initiates that do not require strong write ordering.


### -field MaxPayloadSize

The maximum payload size for the device. Possible values are:




### -field MaxPayload128Bytes

128 byte maximum payload size


### -field MaxPayload256Bytes

256 byte maximum payload size


### -field MaxPayload512Bytes

512 byte maximum payload size


### -field MaxPayload1024Bytes

1024 byte maximum payload size


### -field MaxPayload2048Bytes

2048 byte maximum payload size


### -field MaxPayload4096Bytes

4096 byte maximum payload size

</dd>
</dl>
This value must not exceed the maximum payload size that is specified in the PCIe device capabilities register of the PCIe capability structure.


### -field ExtendedTagEnable

A single bit that indicates that the device is enabled to use an 8-bit Tag field in a PCIe transaction descriptor when the device is a requester. This bit can be set only if the PCIe device capabilities register of the PCIe capability structure indicates that the extended tag size is supported.


### -field PhantomFunctionsEnable

A single bit that indicates that the device is enabled to use unused function numbers (phantom functions) to extend the number of outstanding transactions that are allowed for the device. This bit can be set only if the PCIe device capabilities register of the PCIe capability structure indicates that phantom functions are supported.


### -field AuxPowerEnable

A single bit that indicates that the device is enabled to draw AUX power independent of power management events (PME) AUX power.


### -field NoSnoopEnable

A single bit that indicates that the device is permitted to set the No Snoop bit in the Requester Attributes field of transactions that it initiates that do not require hardware enforced cache coherency.


### -field MaxReadRequestSize

The maximum read request size for the device as a requester. Possible values are:




### -field MaxPayload128Bytes

128 byte maximum read request size


### -field MaxPayload256Bytes

256 byte maximum read request size


### -field MaxPayload512Bytes

512 byte maximum read request size


### -field MaxPayload1024Bytes

1024 byte maximum read request size


### -field MaxPayload2048Bytes

2048 byte maximum read request size


### -field MaxPayload4096Bytes

4096 byte maximum read request size

</dd>
</dl>

### -field BridgeConfigRetryEnable

Reserved.


### -field AsUSHORT

A USHORT representation of the contents of the <b>PCI_EXPRESS_DEVICE_CONTROL_REGISTER</b> structure.


## -remarks
The PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_DEVICE_CONTROL_REGISTER union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

