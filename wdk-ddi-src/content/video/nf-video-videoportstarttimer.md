---
UID: NF.video.VideoPortStartTimer
title: VideoPortStartTimer function
author: windows-driver-content
description: The VideoPortStartTimer function enables calls to a miniport driver's HwVidTimer function.
old-location: display\videoportstarttimer.htm
old-project: display
ms.assetid: d06ae137-d7e8-4e17-82fb-37e5c5e8ad1e
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: VideoPortStartTimer
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
req.alt-api: VideoPortStartTimer
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
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# VideoPortStartTimer function



## -description
The <b>VideoPortStartTimer</b> function enables calls to a miniport driver's <a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a> function.



## -syntax

````
VOID VideoPortStartTimer(
   PVOID HwDeviceExtension
);
````


## -parameters

### -param HwDeviceExtension 

Pointer to the miniport driver's device extension. This pointer is the input parameter to the <i>HwVidTimer</i> function.


## -returns
None


## -remarks
After a miniport driver calls <b>VideoPortStartTimer</b>, its <i>HwVidTimer</i> function is called at approximately one-second intervals until the miniport driver calls <a href="display.videoportstoptimer">VideoPortStopTimer</a>. A miniport driver's <i>HwVidTimer</i> function <i>must not</i> call <b>VideoPortStopTimer</b>.

A miniport driver cannot call <b>VideoPortStartTimer</b> or <b>VideoPortStopTimer</b> if its <a href="display.driverentry_of_video_miniport_driver">DriverEntry</a> function set the <b>HwTimer</b> member of the <a href="display.video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a> structure to <b>NULL</b>. 


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
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.driverentry_of_video_miniport_driver">DriverEntry of Video Miniport Driver</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a>
</dt>
<dt>
<a href="display.video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a>
</dt>
<dt>
<a href="display.videoportstoptimer">VideoPortStopTimer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortStartTimer function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

