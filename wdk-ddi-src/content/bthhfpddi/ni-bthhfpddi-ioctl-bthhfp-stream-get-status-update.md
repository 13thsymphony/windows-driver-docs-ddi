---
UID: NI.bthhfpddi.IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE
title: IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE
author: windows-driver-content
description: The IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE IOCTL Gets a stream channel status update.
old-location: audio\ioctl_bthhfp_stream_get_status_update.htm
old-project: audio
ms.assetid: 1D591422-4ED4-41B9-92E0-189A5EABE7D0
ms.author: windowsdriverdev
ms.date: 11/28/2017
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
req.alt-api: IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE
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

# IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE IOCTL



## -description
<p>The <b>IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE</b> 
   IOCTL Gets a stream channel status update.</p>


## -ioctlparameters

### -input-buffer
<p>A BOOL that is set to TRUE to request an immediate update. Otherwise, set this to FALSE.</p>

### -input-buffer-length
<p>The size of a BOOL.</p>

<p>The size of a BOOL.</p>

### -output-buffer
<p>An NT_STATUS value that represents the new stream channel status. An error status indicates that the synchronous connection-oriented (SCO) channel associated with the stream has been closed, and cannot be reestablished.</p>

<p>An NT_STATUS value that represents the new stream channel status. An error status indicates that the synchronous connection-oriented (SCO) channel associated with the stream has been closed, and cannot be reestablished.</p>

<p>An NT_STATUS value that represents the new stream channel status. An error status indicates that the synchronous connection-oriented (SCO) channel associated with the stream has been closed, and cannot be reestablished.</p>

### -output-buffer-length
<p>The size of an NT_STATUS object.</p>

<p>The size of an NT_STATUS object.</p>

<p>The size of an NT_STATUS object.</p>

<p>The size of an NT_STATUS object.</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>If a request is already pending, then the new request fails and a STATUS_INVALID_DEVICE_REQUEST message is returned.</p>

<p>If a request is pending when an IOCTL_BTHHFP_CLOSE_STREAM_CHANNEL request occurs, then the pending request is canceled and the I/O status block shows STATUS_CANCELLED.</p>

<p>If a request is already pending, then the new request fails and a STATUS_INVALID_DEVICE_REQUEST message is returned.</p>

<p>If a request is pending when an IOCTL_BTHHFP_CLOSE_STREAM_CHANNEL request occurs, then the pending request is canceled and the I/O status block shows STATUS_CANCELLED.</p>

<p>If a request is already pending, then the new request fails and a STATUS_INVALID_DEVICE_REQUEST message is returned.</p>

<p>If a request is pending when an IOCTL_BTHHFP_CLOSE_STREAM_CHANNEL request occurs, then the pending request is canceled and the I/O status block shows STATUS_CANCELLED.</p>

<p>If a request is already pending, then the new request fails and a STATUS_INVALID_DEVICE_REQUEST message is returned.</p>

<p>If a request is pending when an IOCTL_BTHHFP_CLOSE_STREAM_CHANNEL request occurs, then the pending request is canceled and the I/O status block shows STATUS_CANCELLED.</p>

<p>If a request is already pending, then the new request fails and a STATUS_INVALID_DEVICE_REQUEST message is returned.</p>

<p>If a request is pending when an IOCTL_BTHHFP_CLOSE_STREAM_CHANNEL request occurs, then the pending request is canceled and the I/O status block shows STATUS_CANCELLED.</p>

## -remarks
<p>This request will complete immediately if the input parameter is TRUE or if the stream channel status has changed since the last request. Otherwise this request will remain pending until the stream channel status changes or the request is cancelled.</p>

<p>This request is valid only between a successful <a href="..\bthhfpddi\ni-bthhfpddi-ioctl-bthhfp-stream-open.md">IOCTL_BTHHFP_STREAM_OPEN</a> request and subsequent <a href="..\bthhfpddi\ni-bthhfpddi-ioctl-bthhfp-stream-close.md">IOCTL_BTHHFP_STREAM_CLOSE</a> request. If this request is pending when the stream is closed by an <b>IOCTL_BTHHFP_STREAM_CLOSE</b> request, then the pending request is cancelled.</p>

<p>An error status can occur when the Bluetooth link is dropped or other similar conditions occur. Although such conditions are rare, the audio driver must be developed to handle them. This error status can often occur almost simultaneously with a connection status change to FALSE. However the audio driver should not rely on this change of status as a way to determine whether or not the Bluetooth link has been dropped.</p>

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
<a href="audio.bluetooth_hfp_ddi_ioctls">Bluetooth HFP DDI IOCTLs</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_STREAM_GET_STATUS_UPDATE control code%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
