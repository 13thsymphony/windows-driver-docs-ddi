---
UID: NF.video.VideoPortEnableInterrupt
title: VideoPortEnableInterrupt function
author: windows-driver-content
description: The VideoPortEnableInterrupt function is obsolete and should not be called.The VideoPortEnableInterrupt function reenables interrupts from a video adapter after a call to VideoPortDisableInterrupt.
old-location: display\videoportenableinterrupt.htm
old-project: display
ms.assetid: d40b0bc6-fad0-4c83-b1ca-c5105112ae2d
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: VideoPortEnableInterrupt
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
req.alt-api: VideoPortEnableInterrupt
req.alt-loc: Videoprt.sys
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
req.product: Windows 10 or later.
---

# VideoPortEnableInterrupt function



## -description
The <b>VideoPortEnableInterrupt</b> function is <b>obsolete</b> and should not be called.

The <b>VideoPortEnableInterrupt</b> function reenables interrupts from a video adapter after a call to <b>VideoPortDisableInterrupt</b>.



## -syntax

````
VP_STATUS VideoPortEnableInterrupt(
   PVOID HwDeviceExtension
);
````


## -parameters

### -param HwDeviceExtension 

Pointer to the miniport driver's device extension.


## -returns
If <b>VideoPortEnableInterrupt</b> succeeds, it returns NO_ERROR. Otherwise, it returns ERROR_INVALID_FUNCTION.


## -remarks
If you need to disable interrupts for the display adapter, write hardware-specific code to prevent the display adapter from generating interrupts. To subsequently enable interrupts, write hardware-specific code to allow the display adapter to resume generating interrupts.

You should not call <a href="display.videoportdisableinterrupt">VideoPortDisableInterrupt</a> or <b>VideoPortEnableInterrupt</b> for the following reasons:

Can disable interrupts for other devices that share an interrupt vector with the display adapter.

Disables interrupts only on the processor where the current thread is running. On a multiprocessor computer, the display adapter can still interrupt another processor.

On a multiprocessor machine, a call to <b>VideoPortEnableInterrupt</b> might run on a different processor than the previous corresponding call to <b>VideoPortDisableInterrupt</b>. In that case, interrupts will remain disabled for the processor on which <b>VideoPortDisableInterrupt</b> ran.

If the video miniport driver has not registered an <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> routine for the display adapter, <b>VideoPortEnableInterrupt</b> returns ERROR_INVALID_FUNCTION. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 2000 and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>
</dt>
<dt>
<a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a>
</dt>
<dt>
<a href="display.video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a>
</dt>
<dt>
<a href="display.videoportdisableinterrupt">VideoPortDisableInterrupt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortEnableInterrupt function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

