---
UID: NI.bthhfpddi.IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
title: IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT
author: windows-driver-content
description: The IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT IOCTL requests a Handsfree Profile (HFP) Service Level Connection to the Bluetooth device.
old-location: audio\ioctl_bthhfp_device_request_connect.htm
ms.assetid: CE591873-FFDC-49A2-BB75-FE445338D633
ms.author: windowsdriverdev
ms.date: 10/30/2017
ms.topic: ioctl
ms.prod: windows-hardware
ms.technology: audio
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
ms.keywords: BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT
req.iface: 
---

# IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT IOCTL



## -description
<p>The <b>IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT</b> 
   IOCTL requests a Handsfree Profile (HFP) Service Level Connection to the Bluetooth device.</p>


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
<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

## -remarks
<p>This request initiates the procedure to create a Service Level Connection,  and ends without waiting for the connection procedure to complete. Connection status can be determined using <a href="https://msdn.microsoft.com/library/windows/hardware/dn265106">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>.</p>

<p>The audio driver sends this request from its handler for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537369">KSPROPERTY_ONESHOT_RECONNECT</a> KS property.</p>

<p>This request initiates the procedure to create a Service Level Connection,  and ends without waiting for the connection procedure to complete. Connection status can be determined using <a href="https://msdn.microsoft.com/library/windows/hardware/dn265106">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>.</p>

<p>The audio driver sends this request from its handler for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537369">KSPROPERTY_ONESHOT_RECONNECT</a> KS property.</p>

<p>This request initiates the procedure to create a Service Level Connection,  and ends without waiting for the connection procedure to complete. Connection status can be determined using <a href="https://msdn.microsoft.com/library/windows/hardware/dn265106">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>.</p>

<p>The audio driver sends this request from its handler for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537369">KSPROPERTY_ONESHOT_RECONNECT</a> KS property.</p>

<p>This request initiates the procedure to create a Service Level Connection,  and ends without waiting for the connection procedure to complete. Connection status can be determined using <a href="https://msdn.microsoft.com/library/windows/hardware/dn265106">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>.</p>

<p>The audio driver sends this request from its handler for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537369">KSPROPERTY_ONESHOT_RECONNECT</a> KS property.</p>

<p>This request initiates the procedure to create a Service Level Connection,  and ends without waiting for the connection procedure to complete. Connection status can be determined using <a href="https://msdn.microsoft.com/library/windows/hardware/dn265106">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>.</p>

<p>The audio driver sends this request from its handler for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537369">KSPROPERTY_ONESHOT_RECONNECT</a> KS property.</p>

<p>This request initiates the procedure to create a Service Level Connection,  and ends without waiting for the connection procedure to complete. Connection status can be determined using <a href="https://msdn.microsoft.com/library/windows/hardware/dn265106">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>.</p>

<p>The audio driver sends this request from its handler for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537369">KSPROPERTY_ONESHOT_RECONNECT</a> KS property.</p>

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
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265106">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537369">KSPROPERTY_ONESHOT_RECONNECT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_DEVICE_REQUEST_CONNECT control code%20 RELEASE:%20(10/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
