---
UID: NF:video.VideoPortSetEvent
title: VideoPortSetEvent function
author: windows-driver-content
description: The VideoPortSetEvent function sets an event object to the signaled state if it was not already in that state, and returns the event object's previous state.
old-location: display\videoportsetevent.htm
old-project: display
ms.assetid: 93db9d51-3f80-47ff-a2c2-3c937b5dcf7b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortSetEvent, VideoPort_Functions_8efce2e2-f5e7-402a-a5bf-03c23ac85992.xml, VideoPortSetEvent function [Display Devices], video/VideoPortSetEvent, display.videoportsetevent
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
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
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems. Available in Windows XP and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\video\nf-video-videoportclearevent.md">VideoPortClearEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortSetEvent function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>