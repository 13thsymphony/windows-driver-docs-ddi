---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_POINTER_ATTR
title: IOCTL_VIDEO_SET_POINTER_ATTR
author: windows-driver-content
description: Sets the pointer attributes.
old-location: display\ioctl_video_set_pointer_attr.htm
old-project: display
ms.assetid: fa83c6b4-a1e5-49b7-9264-0b2f20748b4b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _TAPE_WRITE_MARKS, TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvdeo.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_VIDEO_SET_POINTER_ATTR
req.alt-loc: Ntddvdeo.h
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
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SET_POINTER_ATTR IOCTL



## -description

Sets the pointer attributes. Support for this modal request is optional. A supporting miniport driver can fail this request (for example, if the attributes specify a larger pointer than the miniport driver can supply). When a miniport driver fails this request, the corresponding display driver must manage the pointer.



Sets the pointer attributes. Support for this modal request is optional. A supporting miniport driver can fail this request (for example, if the attributes specify a larger pointer than the miniport driver can supply). When a miniport driver fails this request, the corresponding display driver must manage the pointer.



## -ioctlparameters

### -input-buffer
The VRP <b>InputBuffer</b> contains the VIDEO_POINTER_ATTRIBUTES structure to be set.


### -input-buffer-length

<text></text>

### -output-buffer
None


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The miniport driver does not set the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddvdeo.h</dt>
</dl>
</td>
</tr>
</table>