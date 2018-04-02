---
UID: NF:video.VideoPortCreateEvent
title: VideoPortCreateEvent function
author: windows-driver-content
description: The VideoPortCreateEvent function creates an event object.
old-location: display\videoportcreateevent.htm
old-project: display
ms.assetid: bb1ef5f0-ccf3-487b-99e6-9ec733c7cd63
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortCreateEvent, VideoPortCreateEvent function [Display Devices], VideoPort_Functions_29412925-5117-4759-b4ea-b4adb4358a8c.xml, display.videoportcreateevent, video/VideoPortCreateEvent
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortCreateEvent
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortCreateEvent function
The <b>VideoPortCreateEvent</b> function creates an event object.

## Syntax

```
VIDEOPORT_API VP_STATUS VideoPortCreateEvent(
  IN PVOID   HwDeviceExtension,
  IN ULONG   EventFlag,
  IN PVOID   Unused,
  OUT PEVENT *ppEvent
);
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`EventFlag`

Specifies the event type and initial event state. This can be an ORed combination of the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
INITIAL_EVENT_SIGNALED

</td>
<td>
Set this flag to indicate the signaled state for the event object. Otherwise, the initial state of the event is nonsignaled.

</td>
</tr>
<tr>
<td>
 NOTIFICATION_EVENT

</td>
<td>
Set this flag to create a notification event. If this flag is not set, a synchronization event is created.

</td>
</tr>
</table>

`Unused`

Is currently ignored by the video port driver and must be set to <b>NULL</b>.

`ppEvent`

Pointer to the memory location at which a pointer to the event object will be returned.


## Return Value

<b>VideoPortCreateEvent</b> returns NO_ERROR if the event object is successfully created.

## Remarks

When a synchronization event is set to the signaled state, a single thread that was waiting for the signaled state is released (its dispatch state transitions from waiting to ready, standby, or running), and the event is automatically reset to the nonsignaled state.

When a notification event is set to the signaled state, all threads that were waiting for the signaled state are released, and the event remains in the signaled state until it is explicitly reset to the nonsignaled state.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570292">VideoPortDeleteEvent</a>