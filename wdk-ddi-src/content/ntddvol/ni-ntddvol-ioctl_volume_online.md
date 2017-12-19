---
UID: NI.ntddvol.IOCTL_VOLUME_ONLINE
title: IOCTL_VOLUME_ONLINE
author: windows-driver-content
description: The IOCTL_VOLUME_ONLINE IOCTL puts the volume in an ONLINE state, which is a state where read and write operations will be executed.
old-location: storage\ioctl_volume_online.htm
old-project: storage
ms.assetid: 3391bda9-2eec-4c03-84ed-76b89e2c0cf0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _VIDEO_WIN32K_CALLBACKS_PARAMS, PVIDEO_WIN32K_CALLBACKS_PARAMS, VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvol.h
req.include-header: Ntddvol.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_VOLUME_ONLINE
req.alt-loc: Ntddvol.h
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

# IOCTL_VOLUME_ONLINE IOCTL



## -description

The <b>IOCTL_VOLUME_ONLINE</b> IOCTL puts the volume in an ONLINE state, which is a state where read and write operations will be executed. The requests are passed down to the physical disk until a subsequent <a href="..\ntddvol\ni-ntddvol-ioctl_volume_offline.md">IOCTL_VOLUME_OFFLINE</a> is received.

A common use for <b>IOCTL_VOLUME_ONLINE</b> is a case in which the mount manager automatically puts a new volume in the ONLINE state when the volume arrives, unless that volume is listed in a registry key that is populated by the cluster service. <b>IOCTL_VOLUME_ONLINE</b> is called for removable drives regardless of the NoAutoMount setting in the following registry key:

HKCU\System\CurrentControlSet\Services\Mountmgr\NoAutoMount

But for volumes controlled by NoAutoMount, assigning a drive letter will cause <b>IOCTL_VOLUME_ONLINE</b> to be called.

For volumes that are controlled by the cluster service, <b>IOCTL_VOLUME_ONLINE</b> is sent by the cluster service when the local node owns the volume. The cluster service uses both <b>IOCTL_VOLUME_ONLINE</b> and <b>IOCTL_VOLUME_ONLINE</b> to allow I/O to a disk volume when the disk volume is owned by the local server. Until the cluster service puts the disk volume in an ONLINE state, no I/O is permitted to the disk volume. This prevents disk volume corruption that could result from multiple cluster nodes writing to the same disk volume simultaneously.



The <b>IOCTL_VOLUME_ONLINE</b> IOCTL puts the volume in an ONLINE state, which is a state where read and write operations will be executed. The requests are passed down to the physical disk until a subsequent <a href="..\ntddvol\ni-ntddvol-ioctl_volume_offline.md">IOCTL_VOLUME_OFFLINE</a> is received.

A common use for <b>IOCTL_VOLUME_ONLINE</b> is a case in which the mount manager automatically puts a new volume in the ONLINE state when the volume arrives, unless that volume is listed in a registry key that is populated by the cluster service. <b>IOCTL_VOLUME_ONLINE</b> is called for removable drives regardless of the NoAutoMount setting in the following registry key:

HKCU\System\CurrentControlSet\Services\Mountmgr\NoAutoMount

But for volumes controlled by NoAutoMount, assigning a drive letter will cause <b>IOCTL_VOLUME_ONLINE</b> to be called.

For volumes that are controlled by the cluster service, <b>IOCTL_VOLUME_ONLINE</b> is sent by the cluster service when the local node owns the volume. The cluster service uses both <b>IOCTL_VOLUME_ONLINE</b> and <b>IOCTL_VOLUME_ONLINE</b> to allow I/O to a disk volume when the disk volume is owned by the local server. Until the cluster service puts the disk volume in an ONLINE state, no I/O is permitted to the disk volume. This prevents disk volume corruption that could result from multiple cluster nodes writing to the same disk volume simultaneously.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Status</b> member is set to STATUS_SUCCESS.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows XP.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddvol.h (include Ntddvol.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddvol\ni-ntddvol-ioctl_volume_offline.md">IOCTL_VOLUME_OFFLINE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_VOLUME_ONLINE control code%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

