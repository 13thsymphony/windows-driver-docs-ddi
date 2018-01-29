---
UID : NI:ntddvdeo.IOCTL_VIDEO_SET_POWER_MANAGEMENT
title : IOCTL_VIDEO_SET_POWER_MANAGEMENT
author : windows-driver-content
description : This IOCTL is obsolete in Windows 2000 and later, and is no longer supported.
old-location : display\ioctl_video_set_power_management.htm
old-project : display
ms.assetid : 76b643db-318c-4dd4-bc45-e9da27ecb283
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.ioctl_video_set_power_management, IOCTL_VIDEO_SET_POWER_MANAGEMENT control code [Display Devices], IOCTL_VIDEO_SET_POWER_MANAGEMENT, ntddvdeo/IOCTL_VIDEO_SET_POWER_MANAGEMENT, Video_IOCTLs_36fe9d13-31c0-435c-939c-af0ce6d5b380.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddvdeo.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SET_POWER_MANAGEMENT IOCTL
This IOCTL is <b>obsolete</b> in Windows 2000 and later, and is no longer supported. A Plug and Play video miniport driver should implement the <a href="..\video\nc-video-pvideo_hw_power_set.md">HwVidSetPowerState</a> function, which provides similar functionality.

Resets the power-consumption level of the adapter to the specified state. As long as the state is <b>VideoPowerOff</b>, the port driver intercepts and fails all IOCTL_VIDEO_<i>XXX</i> requests to the miniport driver until the next IOCTL_VIDEO_SET_POWER_MANAGEMENT request that resets the state to a power-on condition.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The VRP <b>InputBuffer</b> contains the <a href="..\ntddvdeo\ns-ntddvdeo-_video_power_management.md">VIDEO_POWER_MANAGEMENT</a> structure, specifying the state to be set.

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
| **Windows Driver kit version** |  |
| **Header** | ntddvdeo.h |
| **IRQL** |  |

## See Also

<a href="..\ntddvdeo\ns-ntddvdeo-_video_power_management.md">VIDEO_POWER_MANAGEMENT</a>

<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_SET_POWER_MANAGEMENT control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>