---
UID: NI:parallel.IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO
title: IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO
author: windows-driver-content
description: The IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO request returns information about a parallel port.
old-location: parports\ioctl_internal_get_more_parallel_port_info.htm
old-project: parports
ms.assetid: fe5b9b54-b1b6-48e2-b464-f0f3e9845917
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO, IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO control code [Parallel Ports], cisspd_3f4efeec-5579-44c6-8438-bdb4b4983194.xml, parallel/IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO, parports.ioctl_internal_get_more_parallel_port_info
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
-	IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO IOCTL
The <b>IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO</b> request returns information about a parallel port. This information supplements the information that a client obtains by using an <a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a> request. The additional information about the parallel port includes the type of system interface, the bus number, and the interrupt resources used by the port.

For more information, see <a href="https://msdn.microsoft.com/d8ae2296-05b6-419a-93cc-00fcb12d41fe">Obtaining Information About a ParallelPort</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A <a href="..\parallel\ns-parallel-_more_parallel_port_information.md">MORE_PARALLEL_PORT_INFORMATION</a> structure.

### Input Buffer Length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="..\parallel\ns-parallel-_more_parallel_port_information.md">MORE_PARALLEL_PORT_INFORMATION</a> structure.

### Output Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a MORE_PARALLEL_PORT_INFORMATION structure that the client allocates to output parallel port information.

### Output Buffer Length
The size of a MORE_PARALLEL_PORT_INFORMATION structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request succeeds, the <b>Information</b> member is set to the size, in bytes, of the MORE_PARALLEL_PORT_INFORMATION structure. Otherwise; the <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to the following value:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | parallel.h (include Parallel.h) |

## See Also

<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_pnp_info.md">IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</a>



<a href="..\parallel\ns-parallel-_more_parallel_port_information.md">MORE_PARALLEL_PORT_INFORMATION</a>