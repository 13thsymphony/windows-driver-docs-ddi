---
UID: NI.ntddpcm.IOCTL_SOCKET_INFORMATION
title: IOCTL_SOCKET_INFORMATION
author: windows-driver-content
description: This request retrieves socket information for the socket that is indicated by the caller.
old-location: pcmcia\ioctl_socket_information.htm
old-project: PCMCIA
ms.assetid: 95563d68-e812-4c62-9668-8cb25b4735aa
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: PARCLASS_NEGOTIATION_MASK, PARCLASS_NEGOTIATION_MASK, *PPARCLASS_NEGOTIATION_MASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SOCKET_INFORMATION
req.alt-loc: ntddpcm.h
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

# IOCTL_SOCKET_INFORMATION IOCTL



## -description
<p>This request retrieves socket information for the socket that is indicated by the caller. 
</p>


## -ioctlparameters

### -input-buffer
<p><b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION).</p>

<p>The caller initializes the <b>Socket</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a> structure at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. </p>

### -input-buffer-length
<p><b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION).</p>

<p><b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION).</p>

### -output-buffer
<p>The PCMCIA bus driver stores the requested socket data in a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a> at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. </p>

<p>The PCMCIA bus driver stores the requested socket data in a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a> at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. </p>

<p>The PCMCIA bus driver stores the requested socket data in a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a> at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. </p>

### -output-buffer-length
<p>The size of the requested socket data.</p>

<p>The size of the requested socket data.</p>

<p>The size of the requested socket data.</p>

<p>The size of the requested socket data.</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>The <b>Information</b> field is set to the number of bytes read. </p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>If <b>InputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.</p>

<p>If <b>OutputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.</p>

<p>If the bus driver cannot identify a socket that is associated with the socket number indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a>, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If there is no card in the indicated socket, the <b>Status</b> field is set to STATUS_UNSUCCESSFUL.</p>

<p>The <b>Information</b> field is set to the number of bytes read. </p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>If <b>InputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.</p>

<p>If <b>OutputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.</p>

<p>If the bus driver cannot identify a socket that is associated with the socket number indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a>, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If there is no card in the indicated socket, the <b>Status</b> field is set to STATUS_UNSUCCESSFUL.</p>

<p>The <b>Information</b> field is set to the number of bytes read. </p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>If <b>InputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.</p>

<p>If <b>OutputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.</p>

<p>If the bus driver cannot identify a socket that is associated with the socket number indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a>, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If there is no card in the indicated socket, the <b>Status</b> field is set to STATUS_UNSUCCESSFUL.</p>

<p>The <b>Information</b> field is set to the number of bytes read. </p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>If <b>InputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.</p>

<p>If <b>OutputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.</p>

<p>If the bus driver cannot identify a socket that is associated with the socket number indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a>, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If there is no card in the indicated socket, the <b>Status</b> field is set to STATUS_UNSUCCESSFUL.</p>

<p>The <b>Information</b> field is set to the number of bytes read. </p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>If <b>InputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.</p>

<p>If <b>OutputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.</p>

<p>If the bus driver cannot identify a socket that is associated with the socket number indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a>, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If there is no card in the indicated socket, the <b>Status</b> field is set to STATUS_UNSUCCESSFUL.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddpcm.h (include Ntddpcm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCMCIA\buses]:%20IOCTL_SOCKET_INFORMATION control code%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
