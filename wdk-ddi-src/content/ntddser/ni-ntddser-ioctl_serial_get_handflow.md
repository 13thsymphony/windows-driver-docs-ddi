---
UID: NI:ntddser.IOCTL_SERIAL_GET_HANDFLOW
title: IOCTL_SERIAL_GET_HANDFLOW
author: windows-driver-content
description: The IOCTL_SERIAL_GET_HANDFLOW request returns information about the configuration of the handshake flow control set for a serial device.
old-location: serports\ioctl_serial_get_handflow.htm
old-project: serports
ms.assetid: d1d918fb-1ccb-46e6-ad28-e48daf226b3a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SdBusSubmitRequestAsync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SERIAL_GET_HANDFLOW
req.alt-loc: Ntddser.h
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
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_GET_HANDFLOW IOCTL



## -description
The <b>IOCTL_SERIAL_GET_HANDFLOW</b> request returns information about the configuration of the handshake flow control set for a serial device.

To set the configuration of the handshake flow control, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_handflow.md">IOCTL_SERIAL_SET_HANDFLOW</a> request.

For more information about the settings for handshake flow control, see <a href="..\ntddser\ns-ntddser-_serial_handflow.md">SERIAL_HANDFLOW</a>.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_HANDFLOW</b> structure that the serial controller driver uses to output information about the configuration of handshake flow control.


### -output-buffer-length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <b>SERIAL_HANDFLOW</b> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a <b>SERIAL_HANDFLOW</b> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="serial_device_control_requests.htm#generic_status_values_for_serial_device_control_requests">Generic Status Values for Serial Device Control Requests</a>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddser.h (include Ntddser.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_set_handflow.md">IOCTL_SERIAL_SET_HANDFLOW</a>
</dt>
<dt>
<a href="..\ntddser\ns-ntddser-_serial_handflow.md">SERIAL_HANDFLOW</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_GET_HANDFLOW control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

