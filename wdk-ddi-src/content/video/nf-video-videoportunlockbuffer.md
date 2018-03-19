---
UID: NF:video.VideoPortUnlockBuffer
title: VideoPortUnlockBuffer function
author: windows-driver-content
description: The VideoPortUnLockBuffer function unlocks physical pages described by the specified memory descriptor list (MDL).
old-location: display\videoportunlockbuffer.htm
old-project: display
ms.assetid: d5d34f32-026b-4c9f-86ae-a835d4e9c381
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortUnlockBuffer, VideoPortUnlockBuffer function [Display Devices], VideoPort_Functions_2cb5a81f-1956-4431-bf54-7ee6e3d79eab.xml, display.videoportunlockbuffer, video/VideoPortUnlockBuffer
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
-	VideoPortUnlockBuffer
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortUnlockBuffer function
The <b>VideoPortUnLockBuffer</b> function unlocks physical pages described by the specified memory descriptor list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>).

## Syntax

````
VOID VideoPortUnlockBuffer(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID Mdl
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`Mdl`

Pointer to the MDL of the buffer to be released. This parameter should be the same pointer that was returned by <a href="..\video\nf-video-videoportlockbuffer.md">VideoPortLockBuffer</a>.


## Return Value

None


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

<a href="..\video\nf-video-videoportlockbuffer.md">VideoPortLockBuffer</a>