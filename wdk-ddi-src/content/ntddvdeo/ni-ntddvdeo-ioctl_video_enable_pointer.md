---
UID: NI:ntddvdeo.IOCTL_VIDEO_ENABLE_POINTER
title: IOCTL_VIDEO_ENABLE_POINTER
author: windows-driver-content
description: Makes the pointer visible by enabling pointer attributes. Support for this modal request is optional; however, if a miniport driver supports this request, it must process an IOCTL_VIDEO_SET_POINTER_ATTR request before processing this request.
old-location: display\ioctl_video_enable_pointer.htm
old-project: display
ms.assetid: df6d348a-2720-4d47-9bc7-fc0627c951e6
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.ioctl_video_enable_pointer, IOCTL_VIDEO_ENABLE_POINTER control code [Display Devices], IOCTL_VIDEO_ENABLE_POINTER, ntddvdeo/IOCTL_VIDEO_ENABLE_POINTER, Video_IOCTLs_89a9a8cc-bfd6-4969-bb8f-26d72cbaa807.xml
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
-	IOCTL_VIDEO_ENABLE_POINTER
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_ENABLE_POINTER IOCTL
Makes the pointer visible by enabling pointer attributes. Support for this modal request is optional; however, if a miniport driver supports this request, it must process an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_set_pointer_attr.md">IOCTL_VIDEO_SET_POINTER_ATTR</a> request before processing this request.

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

## See Also

<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_set_pointer_attr.md">IOCTL_VIDEO_SET_POINTER_ATTR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_ENABLE_POINTER control code%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>