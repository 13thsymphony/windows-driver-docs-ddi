---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_CURSOR_ATTR
title: IOCTL_VIDEO_QUERY_CURSOR_ATTR
author: windows-driver-content
description: Returns the size, position, and visibility of the cursor.
old-location: display\ioctl_video_query_cursor_attr.htm
old-project: display
ms.assetid: c4ec2813-3e5f-401d-8ad4-cd0682e15e5b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.ioctl_video_query_cursor_attr, IOCTL_VIDEO_QUERY_CURSOR_ATTR control code [Display Devices], IOCTL_VIDEO_QUERY_CURSOR_ATTR, ntddvdeo/IOCTL_VIDEO_QUERY_CURSOR_ATTR, Video_IOCTLs_5c88c1de-006e-4141-9dcd-59d03d51755f.xml
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
-	IOCTL_VIDEO_QUERY_CURSOR_ATTR
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_QUERY_CURSOR_ATTR IOCTL
Returns the size, position, and visibility of the cursor. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers. The cursor position is specified by top and bottom scan lines, instead of row and column information, for VGA-compatible adapters.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None

### Input Buffer Length
<text></text>

### Output Buffer
The miniport driver returns a VIDEO_CURSOR_ATTRIBUTES structure in the VRP <b>OutputBuffer</b>.

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the miniport driver successfully returns the cursor-attribute data, it sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_CURSOR_ATTRIBUTES); otherwise, the miniport driver sets this member to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h |

## See Also

<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_QUERY_CURSOR_ATTR control code%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>