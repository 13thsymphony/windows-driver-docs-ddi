---
UID: NS.VPCI._VPCI_READ_BLOCK_INPUT
title: _VPCI_READ_BLOCK_INPUT
author: windows-driver-content
description: The VPCI_READ_BLOCK_INPUT structure is used in an IOCTL_VPCI_READ_BLOCK IOCTL request to read data from a specified configuration block of data for a PCI Express (PCIe) virtual function (VF).
old-location: kernel\vpci_read_block_input.htm
old-project: kernel
ms.assetid: d8d68231-017a-42fc-ad09-8e7f5cc743d3
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _VPCI_READ_BLOCK_INPUT, VPCI_READ_BLOCK_INPUT, *PVPCI_READ_BLOCK_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: vpci.h
req.include-header: Vpci.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VPCI_READ_BLOCK_INPUT
req.alt-loc: Vpci.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# _VPCI_READ_BLOCK_INPUT structure



## -description
The <b>VPCI_READ_BLOCK_INPUT</b> structure is used in an <a href="..\vpci\ni-vpci-ioctl_vpci_read_block.md">IOCTL_VPCI_READ_BLOCK</a> IOCTL request to read data from a specified configuration block of data for a PCI Express (PCIe) virtual function (VF).

This IOCTL request is issued by the driver of a PCIe  VF on a device that supports the single root I/O virtualization (SR-IOV) interface.



## -syntax

````
typedef struct _VPCI_READ_BLOCK_INPUT {
  ULONG BlockId;
  ULONG BytesRequested;
} VPCI_READ_BLOCK_INPUT, *PVPCI_READ_BLOCK_INPUT;
````


## -struct-fields

### -field BlockId

A <b>ULONG</b> value that specifies the VF configuration block to be read.  This value is defined by the driver for the PCIe physical function (PF) of the device.


### -field BytesRequested

The size, in bytes, of the buffer that receives the block.


## -remarks
A VF configuration block is used for backchannel communication between the drivers of the PCIe PF and a VF on a device that supports the SR-IOV interface. Data from a VF configuration block can be exchanged between the following drivers:

The VF driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.

The PF driver, which runs in the management operating system.

This operating system runs within the Hyper-V parent partition.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Vpci.h (include Vpci.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\vpci\ni-vpci-ioctl_vpci_read_block.md">IOCTL_VPCI_READ_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20VPCI_READ_BLOCK_INPUT structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

