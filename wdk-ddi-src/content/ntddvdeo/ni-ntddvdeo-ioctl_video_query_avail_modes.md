---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_AVAIL_MODES
title: IOCTL_VIDEO_QUERY_AVAIL_MODES
author: windows-driver-content
description: Returns information about each video mode supported by the adapter. Miniport drivers are required to support this nonmodal request.
old-location: display\ioctl_video_query_avail_modes.htm
old-project: display
ms.assetid: 926ec9d5-090c-490d-a0ea-90cc515bdec7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_QUERY_AVAIL_MODES, IOCTL_VIDEO_QUERY_AVAIL_MODES control code [Display Devices], Video_IOCTLs_a846ef88-234e-4867-a3fe-4d8c9b43e00e.xml, display.ioctl_video_query_avail_modes, ntddvdeo/IOCTL_VIDEO_QUERY_AVAIL_MODES
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
-	IOCTL_VIDEO_QUERY_AVAIL_MODES
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_QUERY_AVAIL_MODES IOCTL
Returns information about each video mode supported by the adapter. Miniport drivers are required to support this nonmodal request.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None

### Input Buffer Length
<text></text>

### Output Buffer
The miniport driver returns an array of <a href="..\ntddvdeo\ns-ntddvdeo-_video_mode_information.md">VIDEO_MODE_INFORMATION</a> structures in the VRP <b>OutputBuffer</b>.

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the miniport driver successfully returns the available modes, it sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to (<b>sizeof</b>(VIDEO_MODE_INFORMATION) * <i>NumberOfSupportedModes)</i>; otherwise, the miniport driver sets this member to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h |

## See Also

<a href="..\ntddvdeo\ns-ntddvdeo-_video_mode_information.md">VIDEO_MODE_INFORMATION</a>



<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>