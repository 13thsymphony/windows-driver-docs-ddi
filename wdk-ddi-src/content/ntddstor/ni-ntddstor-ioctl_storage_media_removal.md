---
UID: NI.ntddstor.IOCTL_STORAGE_MEDIA_REMOVAL
title: IOCTL_STORAGE_MEDIA_REMOVAL
author: windows-driver-content
description: Locks the device to prevent removal of the media.
old-location: storage\ioctl_storage_media_removal.htm
old-project: storage
ms.assetid: ea8d7924-7ecc-47df-9616-8e2ed60c3de8
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_STORAGE_MEDIA_REMOVAL
req.alt-loc: Ntddstor.h
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

# IOCTL_STORAGE_MEDIA_REMOVAL IOCTL



## -description

Locks the device to prevent removal of the media. If the driver can prevent the media from being removed while the drive is in use, it disables or enables the mechanism that ejects media on a device - the caller has opened for read or write access.

Unlike <a href="..\ntddstor\ni-ntddstor-ioctl_storage_ejection_control.md">IOCTL_STORAGE_EJECTION_CONTROL</a>, for which the driver tracks requests by caller, the driver ignores IOCTL_STORAGE_MEDIA_REMOVAL unlock requests only if its lock count is already zero, thereby allowing any caller to unlock the drive.

A driver for such a removable-media device that can support this IOCTL must do the following:

<ol>
<li>
Keep a lock count in the device object extension.

</li>
<li>
Keep the lock count per physical device.

</li>
<li>
When called with this IOCTL, if the flag to prevent removing the media is set, increment the count; if the flag is clear, decrement the count.

</li>
<li>
Prevent removal of the media unless all lock counts are zero.

</li>
</ol>


Locks the device to prevent removal of the media. If the driver can prevent the media from being removed while the drive is in use, it disables or enables the mechanism that ejects media on a device - the caller has opened for read or write access.

Unlike <a href="..\ntddstor\ni-ntddstor-ioctl_storage_ejection_control.md">IOCTL_STORAGE_EJECTION_CONTROL</a>, for which the driver tracks requests by caller, the driver ignores IOCTL_STORAGE_MEDIA_REMOVAL unlock requests only if its lock count is already zero, thereby allowing any caller to unlock the drive.

A driver for such a removable-media device that can support this IOCTL must do the following:

Keep a lock count in the device object extension.

Keep the lock count per physical device.

When called with this IOCTL, if the flag to prevent removing the media is set, increment the count; if the flag is clear, decrement the count.

Prevent removal of the media unless all lock counts are zero.



## -ioctlparameters

### -input-buffer
<a id="Input_Buffer"></a><a id="input_buffer"></a><a id="INPUT_BUFFER"></a>Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a Boolean value, with <b>TRUE</b> indicating that the driver should lock the media in the drive.</p>The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>Irp->AssociatedIrp.SystemBuffer contains a Boolean value, with <b>TRUE</b>TRUE indicating that the driver should lock the media in the drive.


### -input-buffer-length

<text></text>

### -output-buffer
<a id="Output_Buffer"></a><a id="output_buffer"></a><a id="OUTPUT_BUFFER"></a>Output Buffer
None</p>None


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
<a id="I_O_Status_Block"></a><a id="i_o_status_block"></a><a id="I_O_STATUS_BLOCK"></a>I/O Status Block
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_DEVICE_NOT_CONNECTED.</p>The <b>Information</b>Information field is set to zero. The <b>Status</b>Status field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_DEVICE_NOT_CONNECTED.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_ejection_control.md">IOCTL_STORAGE_EJECTION_CONTROL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_MEDIA_REMOVAL control code%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

