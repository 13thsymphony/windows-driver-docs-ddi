---
UID: NF.video.VideoPortAcquireDeviceLock
title: VideoPortAcquireDeviceLock function
author: windows-driver-content
description: The VideoPortAcquireDeviceLock function acquires the device lock maintained by the video port driver.
old-location: display\videoportacquiredevicelock.htm
old-project: display
ms.assetid: eeb2d1ad-ad99-4099-9560-8653a627aa08
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: VideoPortAcquireDeviceLock
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
req.alt-api: VideoPortAcquireDeviceLock
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
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# VideoPortAcquireDeviceLock function



## -description
The <b>VideoPortAcquireDeviceLock</b> function acquires the device lock maintained by the video port driver.


## -syntax

````
VOID VideoPortAcquireDeviceLock(
  _In_ PVOID HwDeviceExtension
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.

## -returns
None

## -remarks
Typically, the video port driver guarantees threaded synchronization into the miniport driver through the use of a device lock. However, a miniport driver must perform its own synchronization when being accessed by a child device. That is, a miniport driver must perform synchronization in routines that it exposes through <a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a> by acquiring the device lock maintained by the video port driver.

The miniport driver should release the device lock as quickly as possible by calling <a href="display.videoportreleasedevicelock">VideoPortReleaseDeviceLock</a>.

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
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a>
</dt>
<dt>
<a href="display.videoportreleasedevicelock">VideoPortReleaseDeviceLock</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortAcquireDeviceLock function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
