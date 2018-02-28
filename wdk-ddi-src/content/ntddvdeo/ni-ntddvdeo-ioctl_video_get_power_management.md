---
UID: NI:ntddvdeo.IOCTL_VIDEO_GET_POWER_MANAGEMENT
title: IOCTL_VIDEO_GET_POWER_MANAGEMENT
author: windows-driver-content
description: This IOCTL is obsolete in Windows 2000 and later, and is no longer supported.
old-location: display\ioctl_video_get_power_management.htm
old-project: display
ms.assetid: 5d45b65b-39f6-4a8c-ad88-958e3b950cde
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_VIDEO_GET_POWER_MANAGEMENT, IOCTL_VIDEO_GET_POWER_MANAGEMENT control code [Display Devices], Video_IOCTLs_2595a142-7478-47f5-bb45-1651903f53ab.xml, display.ioctl_video_get_power_management, ntddvdeo/IOCTL_VIDEO_GET_POWER_MANAGEMENT
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
-	IOCTL_VIDEO_GET_POWER_MANAGEMENT
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_GET_POWER_MANAGEMENT IOCTL
This IOCTL is <b>obsolete</b> in Windows 2000 and later, and is no longer supported. A Plug and Play video miniport driver should implement the <a href="..\video\nc-video-pvideo_hw_power_get.md">HwVidGetPowerState</a> function, which provides similar functionality.

Returns the current power-consumption level of the adapter. Support for this nonmodal IOCTL is required for adapters that conform to the VESA DPMS standard.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None

### Input Buffer Length
<text></text>

### Output Buffer
The miniport driver returns a <a href="..\ntddvdeo\ns-ntddvdeo-_video_power_management.md">VIDEO_POWER_MANAGEMENT</a> structure in the VRP <b>OutputBuffer</b>.

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the miniport driver successfully returns the power-consumption information, it sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_POWER_MANAGEMENT); otherwise, the miniport driver sets this member to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h |

## See Also

<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>



<a href="..\ntddvdeo\ns-ntddvdeo-_video_power_management.md">VIDEO_POWER_MANAGEMENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_GET_POWER_MANAGEMENT control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>