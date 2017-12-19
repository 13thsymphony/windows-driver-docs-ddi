---
UID: NS.NTDDVDEO._VIDEO_MEMORY
title: _VIDEO_MEMORY
author: windows-driver-content
description: The VIDEO_MEMORY structure holds the address of a requested block of kernel-mode video memory.
old-location: display\video_memory.htm
old-project: display
ms.assetid: 3d8b3b45-90d9-4e64-a52d-253c9cb86588
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _VIDEO_MEMORY, PVIDEO_MEMORY, *PVIDEO_MEMORY, VIDEO_MEMORY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEO_MEMORY
req.alt-loc: ntddvdeo.h
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

# _VIDEO_MEMORY structure



## -description
The VIDEO_MEMORY structure holds the address of a requested block of kernel-mode video memory.



## -syntax

````
typedef struct _VIDEO_MEMORY {
  PVOID RequestedVirtualAddress;
} VIDEO_MEMORY, *PVIDEO_MEMORY;
````


## -struct-fields

### -field RequestedVirtualAddress

Pointer to the requested virtual address for either the video memory, or the base of video memory, depending on whether <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_map_video_memory.md">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a> or <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_unmap_video_memory.md">IOCTL_VIDEO_UNMAP_VIDEO_MEMORY</a> is using this structure.


## -remarks
VIDEO_MEMORY is used as an input structure to two IOCTLs: <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_map_video_memory.md">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>, and <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_unmap_video_memory.md">IOCTL_VIDEO_UNMAP_VIDEO_MEMORY</a>.

When VIDEO_MEMORY is used with IOCTL_VIDEO_MAP_VIDEO_MEMORY, <b>RequestedVirtualAddress</b> points to the requested virtual address for the video memory. In this case, the value is optional. If zero is specified, the operating system will choose an appropriate location.

When VIDEO_MEMORY is used with IOCTL_VIDEO_UNMAP_VIDEO_MEMORY, <b>RequestedVirtualAddress</b> points to the virtual address of the base of video memory. In this case, the size is implicit since it cannot change (you cannot add video memory dynamically, so it must be the same size as when it was mapped).

For structures used in mapping into user-mode video memory, see <a href="display.video_share_memory">VIDEO_SHARE_MEMORY</a> AND <a href="display.video_share_memory_information">VIDEO_SHARE_MEMORY_INFORMATION</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddvdeo.h (include Ntddvdeo.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_map_video_memory.md">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>
</dt>
<dt>
<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_unmap_video_memory.md">IOCTL_VIDEO_UNMAP_VIDEO_MEMORY</a>
</dt>
<dt>
<a href="display.video_memory_information">VIDEO_MEMORY_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_MEMORY structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

