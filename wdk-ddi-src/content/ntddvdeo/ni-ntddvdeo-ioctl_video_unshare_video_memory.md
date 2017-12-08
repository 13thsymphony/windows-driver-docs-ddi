---
UID: NI.ntddvdeo.IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
title: IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
author: windows-driver-content
description: Unmaps a video hardware frame buffer and video RAM from the virtual address space of the requester that was mapped by an IOCTL_VIDEO_SHARE_VIDEO_MEMORY request.
old-location: display\ioctl_video_unshare_video_memory.htm
old-project: display
ms.assetid: f6ec4237-05f1-4777-a035-7cedb4283e0e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
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
req.alt-api: IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
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
---

# IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY IOCTL



## -description

Unmaps a video hardware frame buffer and video RAM from the virtual address space of the requester that was mapped by an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_share_video_memory.md">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a> request.

Unmaps a video hardware frame buffer and video RAM from the virtual address space of the requester that was mapped by an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_share_video_memory.md">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a> request.


## -ioctlparameters

### -input-buffer
The VRP <b>InputBuffer</b> contains a <a href="display.video_share_memory">VIDEO_SHARE_MEMORY</a> structure specifying the process and the virtual address where the video memory is mapped. The memory is unmapped by calling <a href="display.videoportunmapmemory">VideoPortUnmapMemory</a>.

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
The miniport driver does not set the <b>Information</b> member of the <a href="display.status_block">STATUS_BLOCK</a> structure.

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

## -see-also
<dl>
<dt>
<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_share_video_memory.md">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a>
</dt>
<dt>
<a href="display.video_share_memory">VIDEO_SHARE_MEMORY</a>
</dt>
<dt>
<a href="display.videoportunmapmemory">VideoPortUnmapMemory</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY control code%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
