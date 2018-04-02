---
UID: NS:video._VIDEO_CHILD_STATE
title: "_VIDEO_CHILD_STATE"
author: windows-driver-content
description: The VIDEO_CHILD_STATE structure contains information about a child device and the state into which it should be placed.
old-location: display\video_child_state.htm
old-project: display
ms.assetid: 69a2eebb-9294-4fc1-871a-587792f84f35
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PVIDEO_CHILD_STATE, PVIDEO_CHILD_STATE, PVIDEO_CHILD_STATE structure pointer [Display Devices], VIDEO_CHILD_STATE, VIDEO_CHILD_STATE structure [Display Devices], Video_Structs_330b2d6d-13da-4949-9827-73e7829931b6.xml, _VIDEO_CHILD_STATE, display.video_child_state, video/PVIDEO_CHILD_STATE, video/VIDEO_CHILD_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	VIDEO_CHILD_STATE
product: Windows
targetos: Windows
req.typenames: VIDEO_CHILD_STATE, *PVIDEO_CHILD_STATE
req.product: Windows 10 or later.
---

# _VIDEO_CHILD_STATE structure
The VIDEO_CHILD_STATE structure contains information about a child device and the state into which it should be placed.

## Syntax
```
typedef struct _VIDEO_CHILD_STATE {
  ULONG Id;
  ULONG State;
} VIDEO_CHILD_STATE, *PVIDEO_CHILD_STATE;
```

## Members


`Id`

Specifies the ID for a particular child device, as given to it by the miniport driver. This value is the same as that returned in the <i>UId</i> parameter of the <a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a> function.

`State`

Specifies the new state, on or off, for the child device. A value of one (1) indicates that the child device should be turned on; a value of zero (0) indicates that it should be turned off. One possible use for <b>State</b> is in hotkey switching from one display device to another.

## Remarks
One member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570501">VIDEO_CHILD_STATE_CONFIGURATION</a> structure is an array of VIDEO_CHILD_STATE structures. Each of these structures maintains state information for one of an adapter's child devices.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | video.h (include Video.h) |

## See Also

<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570501">VIDEO_CHILD_STATE_CONFIGURATION</a>