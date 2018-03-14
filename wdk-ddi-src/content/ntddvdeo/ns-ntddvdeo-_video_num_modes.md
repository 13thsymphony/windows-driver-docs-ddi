---
UID: NS:ntddvdeo._VIDEO_NUM_MODES
title: "_VIDEO_NUM_MODES"
author: windows-driver-content
description: The VIDEO_NUM_MODES structure contains the number of modes supported by a video adapter, and the size of the structure that describes each mode.
old-location: display\video_num_modes.htm
old-project: display
ms.assetid: d4ca1276-c0f6-46c6-bf86-3cd2a0c5f194
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVIDEO_NUM_MODES, PVIDEO_NUM_MODES, PVIDEO_NUM_MODES structure pointer [Display Devices], VIDEO_NUM_MODES, VIDEO_NUM_MODES structure [Display Devices], Video_Structs_9e999162-309a-4902-8854-172c672bf1ea.xml, _VIDEO_NUM_MODES, display.video_num_modes, ntddvdeo/PVIDEO_NUM_MODES, ntddvdeo/VIDEO_NUM_MODES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
-	ntddvdeo.h
api_name:
-	VIDEO_NUM_MODES
product: Windows
targetos: Windows
req.typenames: VIDEO_NUM_MODES, *PVIDEO_NUM_MODES
---

# _VIDEO_NUM_MODES structure
The VIDEO_NUM_MODES structure contains the number of modes supported by a video adapter, and the size of the structure that describes each mode.

## Syntax
````
typedef struct _VIDEO_NUM_MODES {
  ULONG NumModes;
  ULONG ModeInformationLength;
} VIDEO_NUM_MODES, *PVIDEO_NUM_MODES;
````

## Members


`ModeInformationLength`

Is the length, in bytes, of the <a href="..\ntddvdeo\ns-ntddvdeo-_video_mode_information.md">VIDEO_MODE_INFORMATION</a> structure that describes each of the modes supported by the device.

`NumModes`

Specifies the number of modes supported by the device.

## Remarks
The miniport driver returns a VIDEO_NUM_MODES structure in response to an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_num_avail_modes.md">IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h (include Ntddvdeo.h) |

## See Also

<a href="..\ntddvdeo\ns-ntddvdeo-_video_mode_information.md">VIDEO_MODE_INFORMATION</a>



<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_num_avail_modes.md">IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_NUM_MODES structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>