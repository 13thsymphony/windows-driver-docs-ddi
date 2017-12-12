---
UID: NI.ntddcdvd.IOCTL_DVD_GET_REGION
title: IOCTL_DVD_GET_REGION
author: windows-driver-content
description: Returns Region Playback Control (RPC) information for a DVD device, such as whether the player supports the RPC2 standard, the current region code of the player, and the remaining number of times the player's region code can be changed by the user.
old-location: storage\ioctl_dvd_get_region.htm
old-project: storage
ms.assetid: 2c3d6962-1d72-47e7-aa7c-226e5a3aa3d4
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: DVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_DVD_GET_REGION
req.alt-loc: Ntddcdvd.h
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

# IOCTL_DVD_GET_REGION IOCTL



## -description

Returns Region Playback Control (RPC) information for a DVD device, such as whether the player supports the RPC2 standard, the current region code of the player, and the remaining number of times the player's region code can be changed by the user. This IOCTL also indicates the region code of the currently mounted disc. This only works if a DVD is in the drive. The <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_key.md">IOCTL_DVD_READ_KEY</a> operation should be used to obtain only the device region code. If the drive region has not been set previously (if it is still at factory default) and if the inserted media has a region, the device region will be set to the current media region.



Returns Region Playback Control (RPC) information for a DVD device, such as whether the player supports the RPC2 standard, the current region code of the player, and the remaining number of times the player's region code can be changed by the user. This IOCTL also indicates the region code of the currently mounted disc. This only works if a DVD is in the drive. The <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_key.md">IOCTL_DVD_READ_KEY</a> operation should be used to obtain only the device region code. If the drive region has not been set previously (if it is still at factory default) and if the inserted media has a region, the device region will be set to the current media region.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The driver returns the <a href="storage.dvd_region">DVD_REGION</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length
None. <b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be &gt;= <b>sizeof(</b>DVD_REGION<b>)</b>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddcdvd.h (include Ntddcdvd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.dvd_region">DVD_REGION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DVD_GET_REGION control code%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

