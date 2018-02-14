---
UID: NS:vpci._VPCI_INVALIDATE_BLOCK_OUTPUT
title: "_VPCI_INVALIDATE_BLOCK_OUTPUT"
author: windows-driver-content
description: The VPCI_INVALIDATE_BLOCK_OUTPUT structure is used in an IOCTL_VPCI_INVALIDATE_BLOCK IOCTL request.
old-location: kernel\vpci_invalidate_block_output.htm
old-project: kernel
ms.assetid: 6971C724-CE5E-44BC-8D3A-FAD248771E6F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: vpci/PVPCI_INVALIDATE_BLOCK_OUTPUT, vpci/VPCI_INVALIDATE_BLOCK_OUTPUT, kernel.vpci_invalidate_block_output, VPCI_INVALIDATE_BLOCK_OUTPUT, _VPCI_INVALIDATE_BLOCK_OUTPUT, PVPCI_INVALIDATE_BLOCK_OUTPUT, PVPCI_INVALIDATE_BLOCK_OUTPUT structure pointer [Kernel-Mode Driver Architecture], *PVPCI_INVALIDATE_BLOCK_OUTPUT, VPCI_INVALIDATE_BLOCK_OUTPUT structure [Kernel-Mode Driver Architecture]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Vpci.h
apiname:
-	VPCI_INVALIDATE_BLOCK_OUTPUT
product: Windows
targetos: Windows
req.typenames: VPCI_INVALIDATE_BLOCK_OUTPUT, *PVPCI_INVALIDATE_BLOCK_OUTPUT
req.product: Windows 10 or later.
---

# _VPCI_INVALIDATE_BLOCK_OUTPUT structure
The <b>VPCI_INVALIDATE_BLOCK_OUTPUT</b> structure is used in an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> IOCTL request.

The driver for a PCI Express (PCIe) virtual function (VF) issues the <b>IOCTL_VPCI_INVALIDATE_BLOCK</b> IOCTL request in order be notified of changes to data in one or more VF configuration blocks. When the IOCTL request is completed, the <b>VPCI_INVALIDATE_BLOCK_OUTPUT</b> structure specifies which VF configuration blocks have been changed.
<div class="alert"><b>Note</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> IOCTL request is issued by the driver of a PCIe  VF on a device that supports the single root I/O virtualization (SR-IOV) interface.</div><div> </div>

## Syntax
````
typedef struct _VPCI_INVALIDATE_BLOCK_OUTPUT {
  UINT64 BlockMask;
} VPCI_INVALIDATE_BLOCK_OUTPUT, *PVPCI_INVALIDATE_BLOCK_OUTPUT;
````

## Members


`BlockMask`

A <b>UINT64</b> value that specifies a bitmask for the first 64 VF configuration blocks. Each bit in the bitmask corresponds to a VF configuration block. If a bit is set to one, the data associated with the corresponding VF configuration block has changed.

## Remarks
A VF configuration block is used for backchannel communication between the drivers of the PCIe PF and a VF on a device that supports the SR-IOV interface. Data from a VF configuration block can be exchanged between the following drivers:

<ul>
<li>
The VF driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.

</li>
<li>
The PF driver, which runs in the management operating system.

This operating system runs within the Hyper-V parent partition.

</li>
</ul>
<div class="alert"><b>Note</b>  The  usage of the VF configuration block and the format of its configuration data are defined by the  independent hardware vendor (IHV) of the device. The configuration data is used only by the drivers of the PF and VF.

However, we recommend that IHVs reserve the first 64 VF configuration blocks for data that may change occasionally. </div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | vpci.h (include Vpci.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20VPCI_INVALIDATE_BLOCK_OUTPUT structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>