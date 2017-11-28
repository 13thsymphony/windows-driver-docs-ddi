---
UID: NI.bthhfpddi.IOCTL_BTHHFP_STREAM_OPEN
title: IOCTL_BTHHFP_STREAM_OPEN
author: windows-driver-content
description: The IOCTL_BTHHFP_STREAM_OPEN IOCTL requests an open synchronous connection-oriented (SCO) channel to transmit audio data over the air.
old-location: audio\ioctl_bthhfp_stream_open.htm
old-project: audio
ms.assetid: 67F42694-C6E1-458E-AE5F-7E3678F55A8B
ms.author: windowsdriverdev
ms.date: 11/21/2017
ms.keywords: BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_BTHHFP_STREAM_OPEN
req.alt-loc: Bthhfpddi.h
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

# IOCTL_BTHHFP_STREAM_OPEN IOCTL



## -description
<p>The <b>IOCTL_BTHHFP_STREAM_OPEN</b> 
   IOCTL requests an open synchronous connection-oriented (SCO) channel to transmit audio data over the air.</p>


## -ioctlparameters

### -input-buffer
<p>N/A</p>

### -input-buffer-length
<p>N/A</p>

<p>N/A</p>

### -output-buffer
<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

### -output-buffer-length
<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>A STATUS_DEVICE_BUSY message to indicate that the stream channel is already open.</p>

<p>A STATUS_DEVICE_BUSY message to indicate that the stream channel is already open.</p>

<p>A STATUS_DEVICE_BUSY message to indicate that the stream channel is already open.</p>

<p>A STATUS_DEVICE_BUSY message to indicate that the stream channel is already open.</p>

<p>A STATUS_DEVICE_BUSY message to indicate that the stream channel is already open.</p>

## -remarks
<p>This request can remain pending for several seconds while resources are established.</p>

<p>While the stream channel is open the target driver attempts to keep the SCO channel open for audio data transfer. However the SCO channel might close briefly, if the remote device disconnects the SCO channel.  The target driver will attempt to reopen the SCO channel in this case, without requiring any action from the client audio driver.</p>

<p>This request can remain pending for several seconds while resources are established.</p>

<p>While the stream channel is open the target driver attempts to keep the SCO channel open for audio data transfer. However the SCO channel might close briefly, if the remote device disconnects the SCO channel.  The target driver will attempt to reopen the SCO channel in this case, without requiring any action from the client audio driver.</p>

<p>This request can remain pending for several seconds while resources are established.</p>

<p>While the stream channel is open the target driver attempts to keep the SCO channel open for audio data transfer. However the SCO channel might close briefly, if the remote device disconnects the SCO channel.  The target driver will attempt to reopen the SCO channel in this case, without requiring any action from the client audio driver.</p>

<p>This request can remain pending for several seconds while resources are established.</p>

<p>While the stream channel is open the target driver attempts to keep the SCO channel open for audio data transfer. However the SCO channel might close briefly, if the remote device disconnects the SCO channel.  The target driver will attempt to reopen the SCO channel in this case, without requiring any action from the client audio driver.</p>

<p>This request can remain pending for several seconds while resources are established.</p>

<p>While the stream channel is open the target driver attempts to keep the SCO channel open for audio data transfer. However the SCO channel might close briefly, if the remote device disconnects the SCO channel.  The target driver will attempt to reopen the SCO channel in this case, without requiring any action from the client audio driver.</p>

<p>This request can remain pending for several seconds while resources are established.</p>

<p>While the stream channel is open the target driver attempts to keep the SCO channel open for audio data transfer. However the SCO channel might close briefly, if the remote device disconnects the SCO channel.  The target driver will attempt to reopen the SCO channel in this case, without requiring any action from the client audio driver.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Bthhfpddi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_STREAM_OPEN control code%20 RELEASE:%20(11/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
