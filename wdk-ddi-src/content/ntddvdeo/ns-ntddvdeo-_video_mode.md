---
UID : NS:ntddvdeo._VIDEO_MODE
title : "_VIDEO_MODE"
author : windows-driver-content
description : The VIDEO_MODE structure contains the requested VGA mode that an adapter should set. This structure is used in conjunction with IOCTL_VIDEO_SET_CURRENT_MODE.
old-location : display\video_mode.htm
old-project : display
ms.assetid : 01fad141-d023-4a3a-80ae-cb07985db8d1
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : VIDEO_MODE, PVIDEO_MODE, *PVIDEO_MODE, ntddvdeo/VIDEO_MODE, VIDEO_MODE structure [Display Devices], ntddvdeo/PVIDEO_MODE, Video_Structs_7a64b36b-d8f2-411d-86e3-4fe854a94220.xml, _VIDEO_MODE, PVIDEO_MODE structure pointer [Display Devices], display.video_mode
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddvdeo.h
req.include-header : Ntddvdeo.h
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
req.typenames : "*PVIDEO_MODE, VIDEO_MODE"
---

# _VIDEO_MODE structure
The VIDEO_MODE structure contains the requested VGA mode that an adapter should set. This structure is used in conjunction with <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_set_current_mode.md">IOCTL_VIDEO_SET_CURRENT_MODE</a>.

## Syntax
````
typedef struct _VIDEO_MODE {
  ULONG RequestedMode;
} VIDEO_MODE, *PVIDEO_MODE;
````

## Members


`RequestedMode`

Is the mode that the miniport driver should set if possible. In addition, the two high-order bits can be set to request special behavior from the miniport driver as follows:




#### VIDEO_MODE_MAP_MEM_LINEAR

Indicates that the miniport driver should map the video memory in a linear fashion if the adapter supports such an operation.


#### VIDEO_MODE_ZERO_MEMORY

Indicates that the miniport driver should zero the video memory in conjunction with the mode set.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h (include Ntddvdeo.h) |