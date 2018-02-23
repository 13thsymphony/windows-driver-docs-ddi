---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_COLOR_REGISTERS
title: IOCTL_VIDEO_SET_COLOR_REGISTERS
author: windows-driver-content
description: Sets the adapter's color registers to the specified RGB values. If the adapter has a color look up table (CLUT), sometimes called a palette, the miniport driver is required to support this modal request.
old-location: display\ioctl_video_set_color_registers.htm
old-project: display
ms.assetid: efaea94e-0cfd-49a7-b8dc-452aa006b024
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.ioctl_video_set_color_registers, IOCTL_VIDEO_SET_COLOR_REGISTERS control code [Display Devices], IOCTL_VIDEO_SET_COLOR_REGISTERS, ntddvdeo/IOCTL_VIDEO_SET_COLOR_REGISTERS, Video_IOCTLs_29dd4eb9-3c05-4b2f-8572-66b7c599fef1.xml
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
-	IOCTL_VIDEO_SET_COLOR_REGISTERS
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SET_COLOR_REGISTERS IOCTL
Sets the adapter's color registers to the specified RGB values. If the adapter has a color look up table (CLUT), sometimes called a palette, the miniport driver is required to support this modal request.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The VRP <b>InputBuffer</b> contains a VIDEO_CLUT structure, specifying an array of RGB values to be set.

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