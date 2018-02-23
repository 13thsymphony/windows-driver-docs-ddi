---
UID: NI:ntddvdeo.IOCTL_VIDEO_SHARE_VIDEO_MEMORY
title: IOCTL_VIDEO_SHARE_VIDEO_MEMORY
author: windows-driver-content
description: This IOCTL is called by a process that will share user-mode video memory as a linear frame buffer.
old-location: display\ioctl_video_share_video_memory.htm
old-project: display
ms.assetid: 7e2e437c-d244-4799-abfc-35fb9d2196d7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.ioctl_video_share_video_memory, IOCTL_VIDEO_SHARE_VIDEO_MEMORY control code [Display Devices], IOCTL_VIDEO_SHARE_VIDEO_MEMORY, ntddvdeo/IOCTL_VIDEO_SHARE_VIDEO_MEMORY, Video_IOCTLs_90056f20-b995-4709-9923-1f7385ebfdce.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddvdeo.h
apiname:
-	IOCTL_VIDEO_SHARE_VIDEO_MEMORY
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SHARE_VIDEO_MEMORY IOCTL
This IOCTL is called by a process that will share user-mode video memory as a linear <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a>. Miniport drivers handle this IOCTL by mapping the frame buffer into the caller's address space with <a href="..\video\nf-video-videoportmapbankedmemory.md">VideoPortMapBankedMemory</a>. Otherwise this IOCTL is the same as <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_map_video_memory.md">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>. 

This request is both modal and nonmodal: the miniport driver must return the location size of the frame buffer within video memory, and the frame buffer size and location can vary from mode to mode (modal characteristic), but a subsequent set-mode operation (to the same mode) must not cause the video memory to change location (nonmodal characteristic).

This IOCTL is DCI only.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The VRP <b>InputBuffer</b> contains a <a href="..\ntddvdeo\ns-ntddvdeo-_video_share_memory.md">VIDEO_SHARE_MEMORY</a> structure specifying a handle to the process mapping the frame buffer, and the requested view size and offset into the shared memory. The view size plus the offset must not exceed the memory size of the adapter.

### Input Buffer Length
<text></text>

### Output Buffer
The miniport driver returns the <a href="..\ntddvdeo\ns-ntddvdeo-_video_share_memory_information.md">VIDEO_SHARE_MEMORY_INFORMATION</a> structure in the VRP <b>OutputBuffer</b>. This output contains the virtual address where the video memory is mapped, the view size in bytes of the mapped memory and the offset into the view.

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the miniport driver successfully maps the memory, it sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_SHARE_MEMORY_INFORMATION); otherwise, the miniport driver sets this member to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h |

## See Also

<a href="..\ntddvdeo\ns-ntddvdeo-_video_share_memory_information.md">VIDEO_SHARE_MEMORY_INFORMATION</a>



<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_map_video_memory.md">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>



<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>



<a href="..\ntddvdeo\ns-ntddvdeo-_video_share_memory.md">VIDEO_SHARE_MEMORY</a>



<a href="..\video\nf-video-videoportmapbankedmemory.md">VideoPortMapBankedMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_SHARE_VIDEO_MEMORY control code%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>