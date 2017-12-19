---
UID: NI.ntddpar.IOCTL_PAR_IS_PORT_FREE
title: IOCTL_PAR_IS_PORT_FREE
author: windows-driver-content
description: The IOCTL_PAR_IS_PORT_FREE request determines if a parallel device's parent parallel port is free at the time the system-supplied bus driver for parallel ports processes the request.
old-location: parports\ioctl_par_is_port_free.htm
old-project: parports
ms.assetid: a64db598-b524-43dd-9831-20cb98cf3c29
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION, OFFLOAD_SECURITY_ASSOCIATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddpar.h
req.include-header: Ntddpar.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_PAR_IS_PORT_FREE
req.alt-loc: ntddpar.h
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
---

# IOCTL_PAR_IS_PORT_FREE IOCTL



## -description

The IOCTL_PAR_IS_PORT_FREE request determines if a parallel device's parent parallel port is free at the time the system-supplied bus driver for parallel ports processes the request. This request is provided primarily for user-mode clients.

This request is processed immediately after the I/O manager calls the parallel port bus driver's dispatch routine for device control requests. Note, however, that the status of the parallel port can change between the time that the parallel port bus driver completes the request and the time that control returns to a user-mode client.

Kernel-mode clients can directly determine if a parallel port is free by calling the system-supplied <a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE</a> callback.

For more information, see <a href="https://msdn.microsoft.com/dbfa962e-9de8-4a9c-b962-24b53c41f35d">Locking and Unlocking a ParallelPort for Use by a Parallel Device</a>.



The IOCTL_PAR_IS_PORT_FREE request determines if a parallel device's parent parallel port is free at the time the system-supplied bus driver for parallel ports processes the request. This request is provided primarily for user-mode clients.

This request is processed immediately after the I/O manager calls the parallel port bus driver's dispatch routine for device control requests. Note, however, that the status of the parallel port can change between the time that the parallel port bus driver completes the request and the time that control returns to a user-mode client.

Kernel-mode clients can directly determine if a parallel port is free by calling the system-supplied <a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE</a> callback.

For more information, see <a href="https://msdn.microsoft.com/dbfa962e-9de8-4a9c-b962-24b53c41f35d">Locking and Unlocking a ParallelPort for Use by a Parallel Device</a>.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a BOOLEAN buffer that the client allocates to output the status of the parallel port. If the parallel port is free, the system-supplied function driver for parallel ports sets the buffer to <b>TRUE</b>, otherwise it sets the buffer to <b>FALSE</b>.


### -output-buffer-length
The length of a BOOLEAN.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> member is set to the size, in bytes, of a BOOLEAN.

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to the following value:



The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is less than the size, in bytes, of a BOOLEAN.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddpar.h (include Ntddpar.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_free.md">IOCTL_INTERNAL_PARALLEL_PORT_FREE</a>
</dt>
<dt>
<a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_PAR_IS_PORT_FREE control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

