---
UID: NI.parallel.IOCTL_INTERNAL_LOCK_PORT_NO_SELECT
title: IOCTL_INTERNAL_LOCK_PORT_NO_SELECT
author: windows-driver-content
description: The IOCTL_INTERNAL_LOCK_PORT_NO_SELECT request allocates the parallel device's parent parallel port, but does not select the parallel device.
old-location: parports\ioctl_internal_lock_port_no_select.htm
old-project: parports
ms.assetid: 4ff7fb02-707f-49a3-a1eb-dcf3353f2803
ms.author: windowsdriverdev
ms.date: 11/30/2017
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
req.alt-api: IOCTL_INTERNAL_LOCK_PORT_NO_SELECT
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

# IOCTL_INTERNAL_LOCK_PORT_NO_SELECT IOCTL



## -description
<p>The <b>IOCTL_INTERNAL_LOCK_PORT_NO_SELECT</b> request allocates the parallel device's parent parallel port, but does not select the parallel device.</p>
<p>This request is only supported in Windows XP and later.</p>
<p>For more information, see <a href="https://msdn.microsoft.com/dbfa962e-9de8-4a9c-b962-24b53c41f35d">Locking and Unlocking a ParallelPort for Use by a Parallel Device</a>.</p>


## -ioctlparameters

### -input-buffer
<p>None.</p>

### -input-buffer-length
<p>None.</p>

<p>None.</p>

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

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel devices.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel devices.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel devices.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel devices.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel devices.</p>

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
<a href="..\parallel\ni-parallel-ioctl-internal-lock-port.md">IOCTL_INTERNAL_LOCK_PORT</a>
</dt>
<dt>
<a href="..\parallel\ni-parallel-ioctl-internal-unlock-port.md">IOCTL_INTERNAL_UNLOCK_PORT</a>
</dt>
<dt>
<a href="..\parallel\ni-parallel-ioctl-internal-unlock-port-no-deselect.md">IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_LOCK_PORT_NO_SELECT control code%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
