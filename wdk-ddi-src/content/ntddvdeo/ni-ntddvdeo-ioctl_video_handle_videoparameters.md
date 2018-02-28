---
UID: NI:ntddvdeo.IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS
title: IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS
author: windows-driver-content
description: Gets the capabilities of the device's television connector and/or copy protection hardware, or sets the desired functionality on the copy protection hardware.
old-location: display\ioctl_video_handle_videoparameters.htm
old-project: display
ms.assetid: 5c48d2b7-3dcc-4025-ab3c-12085369cd7d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS, IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS control code [Display Devices], Video_IOCTLs_c94e510e-22f7-47af-8e82-f84ef2b926c6.xml, display.ioctl_video_handle_videoparameters, ntddvdeo/IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS
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
-	IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS IOCTL
Gets the capabilities of the device's television connector and/or copy protection hardware, or sets the desired functionality on the copy protection hardware. Adapters that support TV connectors should provide support for this modal IOCTL. See <a href="https://msdn.microsoft.com/7d7d44b5-3248-4bee-bc4d-e02fd3c606a7">TV Connector and Copy Protection Support in Video Miniport Drivers</a> for details.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The VRP <b>InputBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570173">VIDEOPARAMETERS</a> structure that describes the action to be performed by the miniport driver.

### Input Buffer Length
<text></text>

### Output Buffer
The miniport driver returns the VIDEOPARAMETERS structure in the VRP <b>OutputBuffer</b>.

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the miniport driver successfully gets or sets the requested information, it sets the <b>Information</b> member of the VRP's <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> to <b>sizeof</b>(VIDEOPARAMETERS); otherwise, the miniport driver sets this member to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h |

## See Also

<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570173">VIDEOPARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>