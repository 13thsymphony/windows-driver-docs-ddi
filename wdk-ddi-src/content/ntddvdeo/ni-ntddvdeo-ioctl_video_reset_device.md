---
UID: NI:ntddvdeo.IOCTL_VIDEO_RESET_DEVICE
title: IOCTL_VIDEO_RESET_DEVICE
author: windows-driver-content
description: Resets the video hardware to the default mode, to which it was initialized at system boot. Miniport drivers are required to support this nonmodal request.
old-location: display\ioctl_video_reset_device.htm
old-project: display
ms.assetid: 98746cae-aed1-4cf4-86d2-eb7cc91e45fc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_VIDEO_RESET_DEVICE, IOCTL_VIDEO_RESET_DEVICE control code [Display Devices], Video_IOCTLs_18bd8312-fd29-4e9c-bd8b-83c5f0e84fbf.xml, display.ioctl_video_reset_device, ntddvdeo/IOCTL_VIDEO_RESET_DEVICE
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
-	IOCTL_VIDEO_RESET_DEVICE
product:
- Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_RESET_DEVICE IOCTL
Resets the video hardware to the default mode, to which it was initialized at system boot. Miniport drivers are required to support this nonmodal request.

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
The miniport driver does not set the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h |