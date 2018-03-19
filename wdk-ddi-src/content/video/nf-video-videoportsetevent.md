---
UID: NF:video.VideoPortSetEvent
title: VideoPortSetEvent function
author: windows-driver-content
description: The VideoPortSetEvent function sets an event object to the signaled state if it was not already in that state, and returns the event object's previous state.
old-location: display\videoportsetevent.htm
old-project: display
ms.assetid: 93db9d51-3f80-47ff-a2c2-3c937b5dcf7b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortSetEvent, VideoPortSetEvent function [Display Devices], VideoPort_Functions_8efce2e2-f5e7-402a-a5bf-03c23ac85992.xml, display.videoportsetevent, video/VideoPortSetEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortSetEvent
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortSetEvent function
The <b>VideoPortSetEvent</b> function sets an event object to the signaled state if it was not already in that state, and returns the event object's previous state.

## Syntax

````
LONG VideoPortSetEvent(
  _In_ PVOID  HwDeviceExtension,
  _In_ PEVENT pEvent
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`pEvent`

Pointer to the event object whose state is to be set.


## Return Value

<b>VideoPortSetEvent</b> returns a nonzero value if the event object was previously in the signaled state.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\video\nf-video-videoportclearevent.md">VideoPortClearEvent</a>