---
UID: NI.mountmgr.IOCTL_MOUNTMGR_CHANGE_NOTIFY
title: IOCTL_MOUNTMGR_CHANGE_NOTIFY
author: windows-driver-content
description: Clients send this IOCTL to the mount manager to be informed whenever there is a change in the mount manager's persistent symbolic link name database.
old-location: storage\ioctl_mountmgr_change_notify.htm
old-project: storage
ms.assetid: ad6ab15b-6789-4ee8-ba99-9eaa6eec070a
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID, MOUNTDEV_UNIQUE_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: mountmgr.h
req.include-header: Mountmgr.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_MOUNTMGR_CHANGE_NOTIFY
req.alt-loc: Mountmgr.h
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

# IOCTL_MOUNTMGR_CHANGE_NOTIFY IOCTL



## -description
Clients send this IOCTL to the mount manager to be informed whenever there is a change in the mount manager's persistent symbolic link name database. 
The mount manager maintains a counter called <i>EpicNumber</i> that records how many changes have occurred in its persistent name database since the last startup. Clients send a number to the mount manager with every change notification request IRP, and the mount manager responds in the following manner:
If the number supplied by the client is not equal to <i>EpicNumber</i>, the mount manager returns STATUS_SUCCESS, indicating that changes have occurred since the client last compared its number with the mount manager's <i>EpicNumber</i>. 
If the number supplied by the client is equal to <i>EpicNumber</i>, the mount manager interprets this as a request to be informed of the next change to the persistent name database, and it queues the change notification IRP and returns STATUS_PENDING. Whenever a change occurs in the database, the mount manager completes all of the pending change notification IRPs, thereby informing clients of the change.
A client that only wants to be informed of the changes to a particular volume is advised to register for Plug and Play target device notification and watch for GUID_IO_VOLUME_NAME_CHANGE.


## -ioctlparameters

### -input-buffer
The mount manager client initializes the <a href="storage.mountmgr_change_notify_info">MOUNTMGR_CHANGE_NOTIFY_INFO</a> structure, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_CHANGE_NOTIFY_INFO).

### -output-buffer
The mount manager returns the current <i>EpicNumber</i> in the <a href="storage.mountmgr_change_notify_info">MOUNTMGR_CHANGE_NOTIFY_INFO</a> structure, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS and the <b>Information</b> field is set to <b>sizeof</b>(MOUNTMGR_CHANGE_NOTIFY_INFO).

If <b>InputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_CHANGE_NOTIFY_INFO) or <b>OutputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_CHANGE_NOTIFY_INFO), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Mountmgr.h (include Mountmgr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.mountmgr_change_notify_info">MOUNTMGR_CHANGE_NOTIFY_INFO</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTMGR_CHANGE_NOTIFY control code%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
