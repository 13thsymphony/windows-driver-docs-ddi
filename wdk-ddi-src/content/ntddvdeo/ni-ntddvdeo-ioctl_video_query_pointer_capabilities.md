---
UID : NI:ntddvdeo.IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES
title : IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES
author : windows-driver-content
description : Returns information about the adapter's &#0034;hardware cursor&#0034; features. Support for this modal request is optional.
old-location : display\ioctl_video_query_pointer_capabilities.htm
old-project : display
ms.assetid : b282dcbe-f2ed-41f2-b97d-e9c409671197
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.ioctl_video_query_pointer_capabilities, IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES control code [Display Devices], IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES, ntddvdeo/IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES, Video_IOCTLs_42064dfd-73fb-4afc-aa3b-4e1ec4829e99.xml
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

# IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES IOCTL
Returns information about the adapter's "hardware cursor" features. Support for this modal request is optional.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None

### Input Buffer Length
<text></text>

### Output Buffer
The miniport driver returns a <a href="..\ntddvdeo\ns-ntddvdeo-_video_pointer_capabilities.md">VIDEO_POINTER_CAPABILITIES</a> structure in the VRP <b>OutputBuffer</b>.

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the miniport driver successfully returns the pointer capabilities, it sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_POINTER_CAPABILITIES); otherwise, the miniport driver sets this member to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddvdeo.h |
| **IRQL** |  |

## See Also

<a href="..\ntddvdeo\ns-ntddvdeo-_video_pointer_capabilities.md">VIDEO_POINTER_CAPABILITIES</a>

<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>