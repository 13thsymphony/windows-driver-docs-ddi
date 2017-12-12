---
UID: NI.bthhfpddi.IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
title: IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
author: windows-driver-content
description: The IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT IOCTL requests a Handsfree Profile (HFP) Service Level Connection to the Bluetooth device.
old-location: audio\ioctl_bthhfp_device_request_connect.htm
old-project: audio
ms.assetid: CE591873-FFDC-49A2-BB75-FE445338D633
ms.author: windowsdriverdev
ms.date: 12/6/2017
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
req.alt-api: IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
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
---

# IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT IOCTL



## -description
The <b>IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT</b> 
   IOCTL requests a Handsfree Profile (HFP) Service Level Connection to the Bluetooth device.



## -ioctlparameters

### -input-buffer
N/A


### -input-buffer-length
N/A


### -output-buffer
N/A


### -output-buffer-length
N/A


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
N/A


## -remarks
This request initiates the procedure to create a Service Level Connection,  and ends without waiting for the connection procedure to complete. Connection status can be determined using <a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_connection_status_update.md">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>.

The audio driver sends this request from its handler for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537369">KSPROPERTY_ONESHOT_RECONNECT</a> KS property.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

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
<dt>
<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_connection_status_update.md">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537369">KSPROPERTY_ONESHOT_RECONNECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT control code%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

