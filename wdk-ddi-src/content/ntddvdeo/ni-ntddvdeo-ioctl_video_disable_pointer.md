---
UID: NI:ntddvdeo.IOCTL_VIDEO_DISABLE_POINTER
title: IOCTL_VIDEO_DISABLE_POINTER
author: windows-driver-content
description: Makes the pointer invisible by disabling the pointer attributes. Support for this modal request is optional.
old-location: display\ioctl_video_disable_pointer.htm
old-project: display
ms.assetid: 0ec5597b-53a4-4711-84f0-d307ad96ef9d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.ioctl_video_disable_pointer, IOCTL_VIDEO_DISABLE_POINTER control code [Display Devices], IOCTL_VIDEO_DISABLE_POINTER, ntddvdeo/IOCTL_VIDEO_DISABLE_POINTER, Video_IOCTLs_b988a11c-2f01-48bb-b07e-2da28f729369.xml
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
-	IOCTL_VIDEO_DISABLE_POINTER
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_DISABLE_POINTER IOCTL
Makes the pointer invisible by disabling the pointer attributes. Support for this modal request is optional.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None

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