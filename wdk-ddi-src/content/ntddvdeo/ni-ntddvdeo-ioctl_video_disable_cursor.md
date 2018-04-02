---
UID: NI:ntddvdeo.IOCTL_VIDEO_DISABLE_CURSOR
title: IOCTL_VIDEO_DISABLE_CURSOR
author: windows-driver-content
description: Makes the cursor invisible by disabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_disable_cursor.htm
old-project: display
ms.assetid: bbc3564d-bed5-45fb-9ee3-ed98073b6eba
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_VIDEO_DISABLE_CURSOR, IOCTL_VIDEO_DISABLE_CURSOR control code [Display Devices], Video_IOCTLs_664ec9f1-497c-4890-b812-9691776b1988.xml, display.ioctl_video_disable_cursor, ntddvdeo/IOCTL_VIDEO_DISABLE_CURSOR
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
-	IOCTL_VIDEO_DISABLE_CURSOR
product:
- Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_DISABLE_CURSOR IOCTL
Makes the cursor invisible by disabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.

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