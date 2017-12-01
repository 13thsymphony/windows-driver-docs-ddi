---
UID: NI.parallel.IOCTL_INTERNAL_SELECT_DEVICE
title: IOCTL_INTERNAL_SELECT_DEVICE
author: windows-driver-content
description: The IOCTL_INTERNAL_SELECT_DEVICE request:Allocates the parallel portThe system-supplied function driver for parallel ports allocates the parallel port if the client does not set the PAR_HAVE_PORT_KEEP_PORT flag in the CommandFlags member of the input PARALLEL_1284_COMMAND structure. Otherwise, the parallel port function driver does not allocate the parallel port.Selects an IEEE 1284.3 daisy chain parallel device or an end-of-chain device attached to the parallel portAlthough a client can select an end-of-chain device using a select device request, Microsoft recommends using an IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE request instead. The parallel port function driver selects the end-of-chain device before it allocates the parallel port to a client.
old-location: parports\ioctl_internal_select_device.htm
old-project: parports
ms.assetid: d072a97d-f15d-44e9-b7d5-4fb872bfcbf0
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: RegisterOpRegionHandler
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
req.alt-api: IOCTL_INTERNAL_SELECT_DEVICE
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
req.irql: 
req.iface: 
---

# IOCTL_INTERNAL_SELECT_DEVICE IOCTL



## -description
<p>
<p>The <b>IOCTL_INTERNAL_SELECT_DEVICE</b> request:</p>
<ul>
<li>
<p>Allocates the parallel port</p>
<p>The system-supplied function driver for parallel ports allocates the parallel port if the client does not set the PAR_HAVE_PORT_KEEP_PORT flag in the <b>CommandFlags</b> member of the input PARALLEL_1284_COMMAND structure. Otherwise, the parallel port function driver does not allocate the parallel port.</p>
</li>
<li>
<p>Selects an IEEE 1284.3 daisy chain parallel device or an end-of-chain device attached to the parallel port</p>
<p>Although a client can select an end-of-chain device using a select device request, Microsoft recommends using an <a href="..\parallel\ni-parallel-ioctl-internal-parallel-port-allocate.md">IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</a> request instead. The parallel port function driver selects the end-of-chain device before it allocates the parallel port to a client.</p>
</li>
</ul>
</p>
<p>The <b>IOCTL_INTERNAL_SELECT_DEVICE</b> request:</p>
<p>Allocates the parallel port</p>
<p>The system-supplied function driver for parallel ports allocates the parallel port if the client does not set the PAR_HAVE_PORT_KEEP_PORT flag in the <b>CommandFlags</b> member of the input PARALLEL_1284_COMMAND structure. Otherwise, the parallel port function driver does not allocate the parallel port.</p>
<p>Selects an IEEE 1284.3 daisy chain parallel device or an end-of-chain device attached to the parallel port</p>
<p>Although a client can select an end-of-chain device using a select device request, Microsoft recommends using an <a href="..\parallel\ni-parallel-ioctl-internal-parallel-port-allocate.md">IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</a> request instead. The parallel port function driver selects the end-of-chain device before it allocates the parallel port to a client.</p>
<p>For more information, see <a href="https://msdn.microsoft.com/1a3ac1b1-9180-4b71-8740-70c6fbe9a885">Selecting and Deselecting an IEEE 1284 Device Attached to a ParallelPort</a>.</p>


## -ioctlparameters

### -input-buffer
<p>The <b>AssociatedIrp.SystemBuffer</b> points to a <a href="..\parallel\ns-parallel--parallel-1284-command.md">PARALLEL_1284_COMMAND</a> structure that the client allocates to input the select device information.</p>

### -input-buffer-length
<p>The <b>Parameters.DeviceIoControl.InputBufferLength</b> member specifies the size, in bytes, of a PARALLEL_1284_COMMAND structure.</p>

<p>The <b>Parameters.DeviceIoControl.InputBufferLength</b> member specifies the size, in bytes, of a PARALLEL_1284_COMMAND structure.</p>

### -output-buffer
<p>None.</p>

<p>None.</p>

<p>None.</p>

### -output-buffer-length
<p>None.</p>

<p>None.</p>

<p>None.</p>

<p>None.</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:</p>

<p></p>

<p>The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_1284_COMMAND structure.</p>

<p>The specified device is not flagged internally as an end-of-chain device and the value of the <b>ID</b> member of the input structure is greater than the number of existing daisy chain devices.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:</p>

<p></p>

<p>The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_1284_COMMAND structure.</p>

<p>The specified device is not flagged internally as an end-of-chain device and the value of the <b>ID</b> member of the input structure is greater than the number of existing daisy chain devices.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:</p>

<p></p>

<p>The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_1284_COMMAND structure.</p>

<p>The specified device is not flagged internally as an end-of-chain device and the value of the <b>ID</b> member of the input structure is greater than the number of existing daisy chain devices.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:</p>

<p></p>

<p>The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_1284_COMMAND structure.</p>

<p>The specified device is not flagged internally as an end-of-chain device and the value of the <b>ID</b> member of the input structure is greater than the number of existing daisy chain devices.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:</p>

<p></p>

<p>The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_1284_COMMAND structure.</p>

<p>The specified device is not flagged internally as an end-of-chain device and the value of the <b>ID</b> member of the input structure is greater than the number of existing daisy chain devices.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Parallel.h (include Parallel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\parallel\ni-parallel-ioctl-internal-deselect-device.md">IOCTL_INTERNAL_DESELECT_DEVICE</a>
</dt>
<dt>
<a href="..\parallel\ns-parallel--parallel-1284-command.md">PARALLEL_1284_COMMAND</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_SELECT_DEVICE control code%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
