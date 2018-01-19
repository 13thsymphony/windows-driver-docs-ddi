---
UID : NS:ntddvdeo._VIDEO_MODE
title : _VIDEO_MODE
author : windows-driver-content
description : The VIDEO_MODE structure contains the requested VGA mode that an adapter should set. This structure is used in conjunction with IOCTL_VIDEO_SET_CURRENT_MODE.
old-location : display\video_mode.htm
old-project : display
ms.assetid : 01fad141-d023-4a3a-80ae-cb07985db8d1
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _VIDEO_MODE, VIDEO_MODE, *PVIDEO_MODE
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
req.alt-api : VIDEO_MODE
req.alt-loc : ntddvdeo.h
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
req.typenames : VIDEO_MODE, *PVIDEO_MODE
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


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddvdeo.h (include Ntddvdeo.h) |