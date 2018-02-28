---
UID: NI:ntddvdeo.IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
title: IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
author: windows-driver-content
description: Unmaps a video hardware frame buffer and video RAM from the virtual address space of the requester that was mapped by an IOCTL_VIDEO_SHARE_VIDEO_MEMORY request.
old-location: display\ioctl_video_unshare_video_memory.htm
old-project: display
ms.assetid: f6ec4237-05f1-4777-a035-7cedb4283e0e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY, IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY control code [Display Devices], Video_IOCTLs_114ef264-3c3f-400d-bef0-4ebd2a4af035.xml, display.ioctl_video_unshare_video_memory, ntddvdeo/IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddvdeo.h
api_name:
-	IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY IOCTL
Unmaps a video hardware frame buffer and video RAM from the virtual address space of the requester that was mapped by an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_share_video_memory.md">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a> request.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The VRP <b>InputBuffer</b> contains a <a href="..\ntddvdeo\ns-ntddvdeo-_video_share_memory.md">VIDEO_SHARE_MEMORY</a> structure specifying the process and the virtual address where the video memory is mapped. The memory is unmapped by calling <a href="..\video\nf-video-videoportunmapmemory.md">VideoPortUnmapMemory</a>.

### Input Buffer Length
<text></text>

### Output Buffer
None

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The miniport driver does not set the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h |

## See Also

<a href="..\video\nf-video-videoportunmapmemory.md">VideoPortUnmapMemory</a>



<a href="..\ntddvdeo\ns-ntddvdeo-_video_share_memory.md">VIDEO_SHARE_MEMORY</a>



<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_share_video_memory.md">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>