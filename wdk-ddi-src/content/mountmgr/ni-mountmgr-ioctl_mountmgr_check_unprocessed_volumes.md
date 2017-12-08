---
UID: NI.mountmgr.IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES
title: IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES
author: windows-driver-content
description: When a volume arrives in the system, it registers for the MOUNTDEV_MOUNTED_DEVICE_GUID interface class and the mount manager receives a Plug and Play notification (see Mount Manager I/O Control Codes for a discussion of this process).
old-location: storage\ioctl_mountmgr_check_unprocessed_volumes.htm
old-project: storage
ms.assetid: 39f486b4-a22e-473b-9a0d-ba2c1046995a
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
req.alt-api: IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES
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

# IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES IOCTL



## -description
When a volume arrives in the system, it registers for the MOUNTDEV_MOUNTED_DEVICE_GUID interface class and the mount manager receives a Plug and Play notification (see <a href="storage.mount_manager_i_o_control_codes">Mount Manager I/O Control Codes</a> for a discussion of this process). When the mount manager receives this notification, it queries the client driver that manages the volume for the volume's unique ID. In some cases, however, particularly with clusters, the client notifies the mount manager of the arrival of its volume, but then does not respond when queried for the volume's unique ID. The mount manager keeps these volumes in a <i>dead mounted device </i>list. Clients can use the IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES IOCTL to request that the mount manager rescan its dead mounted device list and make another attempt to query the clients on the list for the unique IDs of their respective volumes.
This IOCTL is used primarily for cluster support.


## -ioctlparameters

### -input-buffer
None

### -input-buffer-length
None

### -output-buffer
None

### -output-buffer-length
None

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

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