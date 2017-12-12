---
UID: NC.parallel.PPARALLEL_QUERY_WAITERS_ROUTINE
title: PPARALLEL_QUERY_WAITERS_ROUTINE
author: windows-driver-content
description: The PPARALLEL_QUERY_WAITERS_ROUTINE-typed callback routine returns the number of IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE and IOCTL_INTERNAL_SELECT_DEVICE requests that are queued on the work queue of a parallel port.
old-location: parports\pparallel_query_waiters_routine.htm
old-project: parports
ms.assetid: 0fe598b9-2143-4981-b562-6b0f135ec770
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RegisterOpRegionHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: (*PPARALLEL_QUERY_WAITERS_ROUTINE)
req.alt-loc: parallel.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# PPARALLEL_QUERY_WAITERS_ROUTINE callback



## -description
The <i>PPARALLEL_QUERY_WAITERS_ROUTINE</i>-typed callback routine returns the number of <a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_allocate.md">IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</a> and <a href="..\parallel\ni-parallel-ioctl_internal_select_device.md">IOCTL_INTERNAL_SELECT_DEVICE</a> requests that are queued on the work queue of a parallel port. The system-supplied function driver for parallel ports supplies this routine.



## -prototype

````
typedef ULONG (*PPARALLEL_QUERY_WAITERS_ROUTINE)(
  _In_ PVOID QueryAllocsContext
);
````


## -parameters

### -param QueryAllocsContext [in]

Pointer to the device extension of a functional device object (<a href="wdkgloss.f#wdkgloss.fdo#wdkgloss.fdo"><i>FDO</i></a>) that represents a parallel port.


## -returns
The number of requests that are queued on the work queue of the parallel port.


## -remarks
To obtain a pointer to the system-supplied <i>PPARALLEL_QUERY_WAITERS_ROUTINE</i> callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a> request, which returns a <a href="parports.parallel_port_information">PARALLEL_PORT_INFORMATION</a> structure. The <b>QueryNumWaiters</b> member of the PARALLEL_PORT_INFORMATION structure is a pointer to this callback.

A driver can use the <i>PPARALLEL_QUERY_WAITERS_ROUTINE</i> callback to adjust its use of the parallel port based on the number of other clients that are waiting for access to the parallel port. The system-supplied function driver for parallel ports queues only allocate and select requests.

For more information, see <a href="https://msdn.microsoft.com/ea3a1998-9e31-4047-9193-6b402db222c9">Synchronizing the Use of a ParallelPort</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Parallel.h (include Parallel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>
</dt>
<dt>
<a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_allocate.md">IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</a>
</dt>
<dt>
<a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_free.md">IOCTL_INTERNAL_PARALLEL_PORT_FREE</a>
</dt>
<dt>
<a href="parports.parallel_port_information">PARALLEL_PORT_INFORMATION</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PPARALLEL_QUERY_WAITERS_ROUTINE callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

