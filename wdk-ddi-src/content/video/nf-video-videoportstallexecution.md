---
UID: NF:video.VideoPortStallExecution
title: VideoPortStallExecution function
author: windows-driver-content
description: The VideoPortStallExecution function retains control of the processor for the specified number of microseconds and returns to the caller.
old-location: display\videoportstallexecution.htm
old-project: display
ms.assetid: 70b406f8-d9ac-4882-89bc-e257cbe06921
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortStallExecution, video/VideoPortStallExecution, VideoPortStallExecution function [Display Devices], VideoPort_Functions_bda7e25d-a636-4ceb-ae47-c74435f9483a.xml, display.videoportstallexecution
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortStallExecution
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortStallExecution function
The <b>VideoPortStallExecution</b> function retains control of the processor for the specified number of microseconds and returns to the caller.

## Syntax

````
VOID VideoPortStallExecution(
   ULONG Microseconds
);
````

## Parameters

`Microseconds`

Specifies the delay interval, in microseconds.


## Return Value

None

## Remarks

Maximum acceptable values for <i>Microseconds</i> are thousands of microseconds during miniport driver initialization. Otherwise, the given delay interval must be no more than 50 microseconds. In general, <b>VideoPortStallExecution</b> can be called only if the miniport driver must wait for a very few microseconds for its adapter to update state.

While a miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortStallExecution</b>, the miniport driver should be designed to avoid such a call if at all possible. Delays while running at high hardware priorities adversely affect the overall I/O throughput of the system and can freeze the machine.

If a miniport driver has work to be done at regular intervals of more than 50 microseconds, it should implement the <a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a> function. Calls to a miniport driver-supplied <i>HwVidTimer</i> function at approximately one-second intervals can be enabled with <a href="..\video\nf-video-videoportstarttimer.md">VideoPortStartTimer</a> and disabled with <a href="..\video\nf-video-videoportstoptimer.md">VideoPortStopTimer</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems. Available in Windows 2000 and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | Any level |

## See Also

<a href="..\video\nf-video-videoportstoptimer.md">VideoPortStopTimer</a>



<a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a>



<a href="..\video\nf-video-videoportstarttimer.md">VideoPortStartTimer</a>



<a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a>



<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortStallExecution function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>