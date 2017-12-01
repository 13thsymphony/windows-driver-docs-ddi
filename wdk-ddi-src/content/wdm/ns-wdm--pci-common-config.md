---
UID: NS.wdm._PCI_COMMON_CONFIG
title: PCI_COMMON_CONFIG
author: windows-driver-content
description: The PCI_COMMON_CONFIG structure is obsolete.
old-location: kernel\pci_common_config.htm
old-project: kernel
ms.assetid: 239d0c0a-e78e-40d5-b359-36910bdd9358
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PCI_COMMON_CONFIG, PCI_COMMON_CONFIG, *PPCI_COMMON_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCI_COMMON_CONFIG
req.alt-loc: Wdm.h
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

# PCI_COMMON_CONFIG structure



## -description
<p>The <b>PCI_COMMON_CONFIG</b> structure is <u>obsolete</u>. It defines standard PCI configuration information returned by the obsolete <a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a> routine for the input <i>BusDataType</i> PCIConfiguration, assuming the caller-allocated <i>Buffer</i> is of sufficient <i>Length</i>.</p>


## -syntax

````
typedef struct _PCI_COMMON_CONFIG {
  USHORT VendorID;
  USHORT DeviceID;
  USHORT Command;
  USHORT Status;
  UCHAR  RevisionID;
  UCHAR  ProgIf;
  UCHAR  SubClass;
  UCHAR  BaseClass;
  UCHAR  CacheLineSize;
  UCHAR  LatencyTimer;
  UCHAR  HeaderType;
  UCHAR  BIST;
  union {
    struct {
      ULONG BaseAddresses[PCI_TYPE0_ADDRESSES];
      ULONG Reserved1[2];
      ULONG ROMBaseAddress;
      ULONG Reserved2[2];
      UCHAR InterruptLine;
      UCHAR InterruptPin;
      UCHAR MinimumGrant;
      UCHAR MaximumLatency;
    } type0;
  } u;
  UCHAR  DeviceSpecific[192];
} PCI_COMMON_CONFIG, *PPCI_COMMON_CONFIG;
````


## -struct-fields
<dl>

### -field <b>VendorID</b>

<dd>
<p>Identifies the manufacturer of the device. This must be a value allocated by the PCI SIG.</p>
</dd>

### -field <b>DeviceID</b>

<dd>
<p>Identifies the particular device. This value is assigned by the manufacturer.</p>
</dd>

### -field <b>Command</b>

<dd>
<p>Accesses the PCI device's control register. Writing a zero to this register renders the device logically disconnected from the PCI bus except for configuration access. Otherwise, the functionality of the register is device-dependent. Possible system-defined bit encodings for this member include:</p>
<dl>
<dd>
<p>PCI_ENABLE_IO_SPACE</p>
</dd>
<dd>
<p>PCI_ENABLE_MEMORY_SPACE</p>
</dd>
<dd>
<p>PCI_ENABLE_BUS_MASTER</p>
</dd>
<dd>
<p>PCI_ENABLE_SPECIAL_CYCLES</p>
</dd>
<dd>
<p>PCI_ENABLE_WRITE_AND_VALIDATE</p>
</dd>
<dd>
<p>PCI_ENABLE_VGA_COMPATIBLE_PALETTE</p>
</dd>
<dd>
<p>PCI_ENABLE_PARITY</p>
</dd>
<dd>
<p>PCI_ENABLE_WAIT_CYCLE</p>
</dd>
<dd>
<p>PCI_ENABLE_SERR</p>
</dd>
<dd>
<p>PCI_ENABLE_FAST_BACK_TO_BACK</p>
</dd>
</dl>
</dd>

### -field <b>Status</b>

<dd>
<p>Accesses the PCI device's status register. The functionality of this register is device-dependent. Possible system-defined bit encodings for this member include:</p>
<dl>
<dd>
<p>PCI_STATUS_FAST_BACK_TO_BACK             // read-only</p>
</dd>
<dd>
<p>PCI_STATUS_DATA_PARITY_DETECTED</p>
</dd>
<dd>
<p>PCI_STATUS_DEVSEL                                      // 2 bits wide</p>
</dd>
<dd>
<p>PCI_STATUS_SIGNALED_TARGET_ABORT</p>
</dd>
<dd>
<p>PCI_STATUS_RECEIVED_TARGET_ABORT</p>
</dd>
<dd>
<p>PCI_STATUS_RECEIVED_MASTER_ABORT</p>
</dd>
<dd>
<p>PCI_STATUS_SIGNALED_SYSTEM_ERROR</p>
</dd>
<dd>
<p>PCI_STATUS_DETECTED_PARITY_ERROR</p>
</dd>
</dl>
</dd>

### -field <b>RevisionID</b>

<dd>
<p>Specifies the revision level of the device described by the <b>DeviceID</b> member. This value is assigned by the manufacturer. </p>
</dd>

### -field <b>ProgIf</b>

<dd>
<p>Identifies the register-level programming interface, if any, for the device, according to the PCI classification scheme.</p>
</dd>

### -field <b>SubClass</b>

<dd>
<p>Identifies the subtype, if any, of the device, according to the PCI classification scheme.</p>
</dd>

### -field <b>BaseClass</b>

<dd>
<p>Identifies type of the device, according to the PCI classification scheme.</p>
</dd>

### -field <b>CacheLineSize</b>

<dd>
<p>Contains the system cache line size in 32-bit units. This member is relevant only for PCI bus-master devices. The system determines this value during the boot process.</p>
</dd>

### -field <b>LatencyTimer</b>

<dd>
<p>Contains the value of the latency timer in units of PCI bus clocks. This member is relevant only for PCI bus-master devices. The system determines this value during the boot process.</p>
</dd>

### -field <b>HeaderType</b>

<dd>
<p>The system ORs the value of this member with PCI_MULTIFUNCTION, if appropriate to the device. The value of this member indicates the PCI_HEADER_TYPE_0 layout that follows.</p>
</dd>

### -field <b>BIST</b>

<dd>
<p>Zero indicates that the device does not support built-in self-test. Otherwise, the device supports built-in self-test according to the PCI standard.</p>
</dd>

### -field <b>u</b>

<dd>
<dl>

### -field <b>type0</b>

<dd>
<p>Drivers call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546580">HalAssignSlotResources</a> to configure these values and to get back the bus-relative values passed to other configuration routines.</p>
<dl>

### -field <b>BaseAddresses</b>

<dd>
<p>Base addresses.</p>
</dd>

### -field <b>Reserved1</b>

<dd>
<p>Reserved.</p>
</dd>

### -field <b>ROMBaseAddress</b>

<dd>
<p>ROM base address.</p>
</dd>

### -field <b>Reserved2</b>

<dd>
<p>Reserved.</p>
</dd>

### -field <b>InterruptLine</b>

<dd>
<p>Interrupt line number.</p>
</dd>

### -field <b>InterruptPin</b>

<dd>
<p>Interrupt pin number.</p>
</dd>

### -field <b>MinimumGrant</b>

<dd>
<p>Minimum grant.</p>
</dd>

### -field <b>MaximumLatency</b>

<dd>
<p>Maximum latency.</p>
</dd>
</dl>
</dd>
</dl>
</dd>

### -field <b>DeviceSpecific</b>

<dd>
<p>Contains any device-specific initialization information that is available.</p>
</dd>
</dl>

## -remarks
<p>Certain members of this structure have read-only values, so attempts to reset them are ignored. These members include the following: <b>VendorID</b>, <b>DeviceID</b>, <b>RevisionID</b>, <b>ProgIf</b>, <b>SubClass</b>, <b>BaseClass</b>, <b>HeaderType</b>, <b>InterruptPin</b>, <b>MinimumGrant</b>, and <b>MaximumLatency.</b></p>

<p>Other members are provisionally read-only: that is, the system initializes them to their correct values, so drivers can safely treat them as read-only. However, they can be reset if a bus-master driver finds it necessary. These members include the following: <b>CacheLineSize</b> and <b>LatencyTimer</b>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546580">HalAssignSlotResources</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546628">HalSetBusData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546633">HalSetBusDataByOffset</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCI_COMMON_CONFIG structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
