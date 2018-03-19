---
UID: NI:parallel.IOCTL_INTERNAL_PARALLEL_PORT_FREE
title: IOCTL_INTERNAL_PARALLEL_PORT_FREE
author: windows-driver-content
description: The IOCTL_INTERNAL_PARALLEL_PORT_FREE request frees a parallel port.
old-location: parports\ioctl_internal_parallel_port_free.htm
old-project: parports
ms.assetid: bdf44009-4898-4890-9441-918e1647566d
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_PARALLEL_PORT_FREE, IOCTL_INTERNAL_PARALLEL_PORT_FREE control code [Parallel Ports], cisspd_ec1947dc-7124-445b-8b4a-759d6cba8225.xml, parallel/IOCTL_INTERNAL_PARALLEL_PORT_FREE, parports.ioctl_internal_parallel_port_free
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
-	IOCTL_INTERNAL_PARALLEL_PORT_FREE
product: Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_PARALLEL_PORT_FREE IOCTL
The <b>IOCTL_INTERNAL_PARALLEL_PORT_FREE</b> request frees a parallel port. After using a parallel port, a client must free it. Microsoft recommends using the system-supplied <a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE</a> callback to free a parallel port because there is no functional advantage to using an <b>IOCTL_INTERNAL_PARALLEL_PORT_FREE</b> request to free the port.

For more information, see <a href="https://msdn.microsoft.com/ea3a1998-9e31-4047-9193-6b402db222c9">Synchronizing the Use of a ParallelPort</a>.

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

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | parallel.h (include Parallel.h) |

## See Also

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_allocate.md">IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</a>



<a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE</a>