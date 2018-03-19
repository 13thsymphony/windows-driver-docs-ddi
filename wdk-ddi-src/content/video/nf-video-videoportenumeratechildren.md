---
UID: NF:video.VideoPortEnumerateChildren
title: VideoPortEnumerateChildren function
author: windows-driver-content
description: The VideoPortEnumerateChildren function allows a video miniport driver to force a reenumeration of its child devices.
old-location: display\videoportenumeratechildren.htm
old-project: display
ms.assetid: 41f081f3-4079-46f8-9d22-76a2d9e992b5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortEnumerateChildren, VideoPortEnumerateChildren function [Display Devices], VideoPort_Functions_8bc790f2-319f-41a6-9bf7-02a8605d2cc1.xml, display.videoportenumeratechildren, video/VideoPortEnumerateChildren
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
-	VideoPortEnumerateChildren
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortEnumerateChildren function
The <b>VideoPortEnumerateChildren</b> function allows a video miniport driver to force a reenumeration of its child devices.

## Syntax

````
VP_STATUS VideoPortEnumerateChildren(
  _In_       PVOID HwDeviceExtension,
  _Reserved_ PVOID Reserved
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`Reserved`

Must be set to <b>NULL</b>.


## Return Value

<b>VideoPortEnumerateChildren</b> returns NO_ERROR.

## Remarks

Some devices generate an interrupt when new hardware is connected to the system, or when existing hardware is disconnected from the system. For these devices, <b>VideoPortEnumerateChildren</b> can make such system changes as seamless as possible. The following is one possible scenario that forces the reenumeration of child devices through <b>VideoPortEnumerateChildren</b>:

<ul>
<li>
New hardware is connected, which generates an interrupt.

</li>
<li>
The miniport driver's interrupt handler (<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>) queues a DPC routine (<a href="..\video\nc-video-pminiport_dpc_routine.md">HwVidDpcRoutine</a>) by calling <a href="..\video\nf-video-videoportqueuedpc.md">VideoPortQueueDpc</a>.

</li>
<li>
The asynchronously executed DPC contains a call to <b>VideoPortEnumerateChildren</b>.

</li>
</ul>
<b>VideoPortEnumerateChildren</b> causes <a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a> to be called, allowing the Plug and Play Manager to enumerate all of the adapter's child devices.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\video\nc-video-pminiport_dpc_routine.md">HwVidDpcRoutine</a>



<a href="..\video\nf-video-videoportqueuedpc.md">VideoPortQueueDpc</a>



<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>



<a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>