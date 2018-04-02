---
UID: NI:parallel.IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT
title: IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT
author: windows-driver-content
description: The IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT request frees a parallel device's parent parallel port.
old-location: parports\ioctl_internal_unlock_port_no_deselect.htm
old-project: parports
ms.assetid: 516441bc-d240-43d2-a206-3d0bd8e712e9
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT, IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT control code [Parallel Ports], cisspd_a62d2a09-93e4-4fc4-ac5d-9589d930c794.xml, parallel/IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT, parports.ioctl_internal_unlock_port_no_deselect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: parallel.h
req.include-header: Parallel.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	parallel.h
api_name:
-	IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT IOCTL
The <b>IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT</b> request frees a parallel device's parent parallel port. The request does not deselect the parallel device on the parallel port. 

This request is only supported in Windows XP and later.

For more information, see <a href="https://msdn.microsoft.com/dbfa962e-9de8-4a9c-b962-24b53c41f35d">Locking and Unlocking a ParallelPort for Use by a Parallel Device</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel devices.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | parallel.h (include Parallel.h) |

## See Also

<a href="..\parallel\ni-parallel-ioctl_internal_unlock_port.md">IOCTL_INTERNAL_UNLOCK_PORT</a>



<a href="..\parallel\ni-parallel-ioctl_internal_lock_port_no_select.md">IOCTL_INTERNAL_LOCK_PORT_NO_SELECT</a>



<a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a>