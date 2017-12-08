---
UID: NI.ks.IOCTL_KS_HANDSHAKE
title: IOCTL_KS_HANDSHAKE
author: windows-driver-content
description: A kernel-mode client can use IOCTL_KS_HANDSHAKE to negotiate an interface between unconnected AVStream pins.
old-location: stream\ioctl_ks_handshake.htm
old-project: stream
ms.assetid: 63c50af0-365b-4074-a703-9e43b1514a55
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _KsEdit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_KS_HANDSHAKE
req.alt-loc: ks.h
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

# IOCTL_KS_HANDSHAKE IOCTL



## -description

A kernel-mode client can use IOCTL_KS_HANDSHAKE to negotiate an interface between unconnected AVStream pins. The client calls <a href="stream.kssynchronousdevicecontrol">KsSynchronousDeviceControl</a> with IOCTL_KS_HANDSHAKE and the parameters described below.
To attempt a protocol handshake with a pin that is already connected, call <a href="stream.kspinhandshake">KsPinHandshake</a>.

A kernel-mode client can use IOCTL_KS_HANDSHAKE to negotiate an interface between unconnected AVStream pins. The client calls <a href="stream.kssynchronousdevicecontrol">KsSynchronousDeviceControl</a> with IOCTL_KS_HANDSHAKE and the parameters described below.
To attempt a protocol handshake with a pin that is already connected, call <a href="stream.kspinhandshake">KsPinHandshake</a>.


## -ioctlparameters

### -input-buffer
The client places a pointer to a structure of type <a href="stream.kshandshake">KSHANDSHAKE</a> in the <b>InBuffer</b> parameter. 

### -input-buffer-length
<b>InLength </b>must be equal to sizeof(KSHANDSHAKE).

### -output-buffer
The client places a pointer to a structure of type <a href="stream.kshandshake">KSHANDSHAKE</a> in the <b>OutBuffer</b> parameter. If the request is successful, handshake information is placed in this location.

### -output-buffer-length
<b>OutLength </b>must be equal to sizeof(KSHANDSHAKE).

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, IoStatus.Information is set to sizeof(KSHANDSHAKE).

This IOCTL can be sent from kernel-mode only. If the request is sent from user mode, the Status member is set to STATUS_INVALID_DEVICE_REQUEST. 

If the <b>InLength</b> and <b>OutLength</b> parameters in the call to <b>KsSynchronousDeviceControl</b> are not both equal to sizeof(KSHANDSHAKE), the Status member is set to STATUS_INVALID_BUFFER_SIZE.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.kshandshake">KSHANDSHAKE</a>
</dt>
<dt>
<a href="stream.kspinhandshake">KsPinHandshake</a>
</dt>
<dt>
<a href="stream.kspinregisterhandshakecallback">KsPinRegisterHandshakeCallback</a>
</dt>
<dt>
<a href="stream.avstrminipinhandshake">AVStrMiniPinHandshake</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IOCTL_KS_HANDSHAKE control code%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
