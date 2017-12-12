---
UID: NI.ntddvdeo.IOCTL_VIDEO_SHARE_VIDEO_MEMORY
title: IOCTL_VIDEO_SHARE_VIDEO_MEMORY
author: windows-driver-content
description: This IOCTL is called by a process that will share user-mode video memory as a linear frame buffer.
old-location: display\ioctl_video_share_video_memory.htm
old-project: display
ms.assetid: 7e2e437c-d244-4799-abfc-35fb9d2196d7
ms.author: windowsdriverdev
ms.date: 12/8/2017
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
req.alt-api: IOCTL_VIDEO_SHARE_VIDEO_MEMORY
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

# IOCTL_VIDEO_SHARE_VIDEO_MEMORY IOCTL



## -description

This IOCTL is called by a process that will share user-mode video memory as a linear <a href="wdkgloss.f#wdkgloss.frame_buffer#wdkgloss.frame_buffer"><i>frame buffer</i></a>. Miniport drivers handle this IOCTL by mapping the frame buffer into the caller's address space with <a href="display.videoportmapbankedmemory">VideoPortMapBankedMemory</a>. Otherwise this IOCTL is the same as <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_map_video_memory.md">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>. 

This request is both modal and nonmodal: the miniport driver must return the location size of the frame buffer within video memory, and the frame buffer size and location can vary from mode to mode (modal characteristic), but a subsequent set-mode operation (to the same mode) must not cause the video memory to change location (nonmodal characteristic).

This IOCTL is DCI only.



This IOCTL is called by a process that will share user-mode video memory as a linear <a href="wdkgloss.f#wdkgloss.frame_buffer#wdkgloss.frame_buffer"><i>frame buffer</i></a>. Miniport drivers handle this IOCTL by mapping the frame buffer into the caller's address space with <a href="display.videoportmapbankedmemory">VideoPortMapBankedMemory</a>. Otherwise this IOCTL is the same as <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_map_video_memory.md">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>. 

This request is both modal and nonmodal: the miniport driver must return the location size of the frame buffer within video memory, and the frame buffer size and location can vary from mode to mode (modal characteristic), but a subsequent set-mode operation (to the same mode) must not cause the video memory to change location (nonmodal characteristic).

This IOCTL is DCI only.



## -ioctlparameters

### -input-buffer
The VRP <b>InputBuffer</b> contains a <a href="display.video_share_memory">VIDEO_SHARE_MEMORY</a> structure specifying a handle to the process mapping the frame buffer, and the requested view size and offset into the shared memory. The view size plus the offset must not exceed the memory size of the adapter.


### -input-buffer-length

<text></text>

### -output-buffer
The miniport driver returns the <a href="display.video_share_memory_information">VIDEO_SHARE_MEMORY_INFORMATION</a> structure in the VRP <b>OutputBuffer</b>. This output contains the virtual address where the video memory is mapped, the view size in bytes of the mapped memory and the offset into the view. 


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the miniport driver successfully maps the memory, it sets the <b>Information</b> member of the <a href="display.status_block">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_SHARE_MEMORY_INFORMATION); otherwise, the miniport driver sets this member to zero.


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
<a href="display.videoportmapbankedmemory">VideoPortMapBankedMemory</a>
</dt>
<dt>
<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_map_video_memory.md">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>
</dt>
<dt>
<a href="display.video_share_memory">VIDEO_SHARE_MEMORY</a>
</dt>
<dt>
<a href="display.video_share_memory_information">VIDEO_SHARE_MEMORY_INFORMATION</a>
</dt>
<dt>
<a href="display.status_block">STATUS_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_SHARE_VIDEO_MEMORY control code%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

