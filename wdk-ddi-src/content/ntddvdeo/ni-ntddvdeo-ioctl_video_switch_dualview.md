---
UID : NI:ntddvdeo.IOCTL_VIDEO_SWITCH_DUALVIEW
title : IOCTL_VIDEO_SWITCH_DUALVIEW
author : windows-driver-content
description : Notifies the video miniport that a secondary view is about to be enabled or disabled.
old-location : display\ioctl_video_switch_dualview.htm
old-project : display
ms.assetid : 09fe033f-7876-4b23-baf6-5afe0866bb1d
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.ioctl_video_switch_dualview, IOCTL_VIDEO_SWITCH_DUALVIEW control code [Display Devices], IOCTL_VIDEO_SWITCH_DUALVIEW, ntddvdeo/IOCTL_VIDEO_SWITCH_DUALVIEW, Video_IOCTLs_424b313b-2f68-4284-97d6-596f1407ee96.xml
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

# IOCTL_VIDEO_SWITCH_DUALVIEW IOCTL
Notifies the video miniport that a secondary view is about to be enabled or disabled. A secondary view is enabled by a call to the video port driver's <a href="..\video\nf-video-videoportcreatesecondarydisplay.md">VideoPortCreateSecondaryDisplay</a>.

Windows XP and later send this request to the video miniport driver to notify it of a secondary view change of status. Video miniport drivers can use this notification to make video memory arrangements in advance. For example, when the display driver sets the mode of the primary view, it can reserve video memory for one or more secondary views. 

<div class="alert"><b>Note</b>    This request, which is available in Windows XP and later, can only be used to manage video memory.</div>
<div> </div>

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The VRP <b>InputBuffer</b> contains a pointer to a ULONG, which can be one of the two following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
The device is about to be detached.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
The device is about to be attached.

</td>
</tr>
</table>

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

<a href="..\video\nf-video-videoportcreatesecondarydisplay.md">VideoPortCreateSecondaryDisplay</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_SWITCH_DUALVIEW control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>