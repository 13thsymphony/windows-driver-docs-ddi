---
UID: NI.mountmgr.IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION
title: IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION
author: windows-driver-content
description: This IOCTL allows a client to simulate a Plug and Play device interface arrival notification with the given volume name.
old-location: storage\ioctl_mountmgr_volume_arrival_notification.htm
ms.assetid: 0c27c49e-a06c-4781-9d7f-50f15f9715ac
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: ioctl
ms.prod: windows-hardware
ms.technology: Storage
req.header: mountmgr.h
req.include-header: Mountmgr.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION
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
ms.keywords: MOUNTDEV_UNIQUE_ID, MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID
req.iface: 
---

# IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION IOCTL



## -description
<p>This IOCTL allows a client to simulate a Plug and Play device interface arrival notification with the given volume name. If a client does not register a device interface of type MOUNTDEV_MOUNTED_DEVICE_GUID, the mount manager is not alerted of its arrival. However, the client can alert the mount manager of its volume's arrival directly by means of this IOCTL.</p>
<p>This IOCTL allows clients to obtain drive letters for newly created volumes during text mode setup when the Plug and Play device installer is not running.</p>
<p>Clients that have registered a device interface of type MOUNTDEV_MOUNTED_DEVICE_GUID in the normal way should not use this IOCTL. </p>


## -ioctlparameters

### -input-buffer
<p>The mount manager client loads the following structure with the nonpersistent target device name. The initialized structure, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562289">MOUNTMGR_TARGET_NAME</a>, defined in <i>Mountmgr.h</i>, is inserted at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.</p>

### -input-buffer-length
<p><b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_TARGET_NAME).</p>

<p><b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_TARGET_NAME).</p>

### -output-buffer
<p>None</p>

<p>None</p>

<p>None</p>

### -output-buffer-length
<p>None</p>

<p>None</p>

<p>None</p>

<p>None</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

<p>If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.</p>

<p>The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562289">MOUNTMGR_TARGET_NAME</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION control code%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
