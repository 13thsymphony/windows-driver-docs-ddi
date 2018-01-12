---
UID: NI:ntddvol.IOCTL_VOLUME_IS_CLUSTERED
title: IOCTL_VOLUME_IS_CLUSTERED
author: windows-driver-content
description: Allows a driver or application to determine if a volume is clustered.
old-location: storage\ioctl_volume_is_clustered.htm
old-project: storage
ms.assetid: aa8accf8-79c9-4868-b621-d468a121cb60
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _VIDEO_WIN32K_CALLBACKS_PARAMS, VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS
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
req.alt-api: IOCTL_VOLUME_IS_CLUSTERED
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
req.typenames: VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS
---

# IOCTL_VOLUME_IS_CLUSTERED IOCTL



## -description
Allows  a driver or application to determine if a volume is clustered.



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
 If the volume is clustered, the IOCTL returns <b>STATUS_SUCCESS</b>. If the volume is not clustered, the IOCTL returns  <b>STATUS_UNSUCCESSFUL</b>.


## -remarks
For an invalid disk type, such as dynamic disk, the disk management component will return <b>STATUS_INVALID_DEVICE_REQUEST</b>.


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