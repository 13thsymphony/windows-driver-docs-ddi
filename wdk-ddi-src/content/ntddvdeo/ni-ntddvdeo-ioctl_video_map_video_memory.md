---
UID: NI:ntddvdeo.IOCTL_VIDEO_MAP_VIDEO_MEMORY
title: IOCTL_VIDEO_MAP_VIDEO_MEMORY
author: windows-driver-content
description: Maps the video hardware frame buffer and video RAM into the virtual address space of the requester.
old-location: display\ioctl_video_map_video_memory.htm
old-project: display
ms.assetid: 9e17502a-b5bf-4f17-8e74-1974f7e65e01
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_MAP_VIDEO_MEMORY, IOCTL_VIDEO_MAP_VIDEO_MEMORY control code [Display Devices], Video_IOCTLs_8a343fc8-9ebe-4079-a175-94d39222adee.xml, display.ioctl_video_map_video_memory, ntddvdeo/IOCTL_VIDEO_MAP_VIDEO_MEMORY
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
-	IOCTL_VIDEO_MAP_VIDEO_MEMORY
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_MAP_VIDEO_MEMORY IOCTL
Maps the video hardware <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a> and video RAM into the virtual address space of the requester. Miniport drivers are required to handle this IOCTL and to map all video memory in the caller's address space with <a href="..\video\nf-video-videoportmapmemory.md">VideoPortMapMemory</a>. 

This request is both modal and nonmodal: the miniport driver must return the location size of the frame buffer within video memory, and the frame buffer size and location can vary from mode to mode (modal characteristic). However, a subsequent set-mode operation (to the same mode) must not cause the video memory to change location (nonmodal characteristic).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The VRP <b>InputBuffer</b> contains a <a href="..\ntddvdeo\ns-ntddvdeo-_video_memory.md">VIDEO_MEMORY</a> structure specifying either a requested virtual base address or zero, which requests the system to assign a virtual base address mapped to the adapter's RAM and frame buffer range(s).

### Input Buffer Length
<text></text>

### Output Buffer
The miniport driver returns a <a href="..\ntddvdeo\ns-ntddvdeo-_video_memory_information.md">VIDEO_MEMORY_INFORMATION</a> structure in the VRP <b>OutputBuffer</b>.

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the miniport driver successfully maps the memory, it sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_MEMORY_INFORMATION); otherwise, it sets this member to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h |

## See Also

<a href="..\video\nf-video-videoportmapmemory.md">VideoPortMapMemory</a>



<a href="..\ntddvdeo\ns-ntddvdeo-_video_memory_information.md">VIDEO_MEMORY_INFORMATION</a>



<a href="..\ntddvdeo\ns-ntddvdeo-_video_memory.md">VIDEO_MEMORY</a>



<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>