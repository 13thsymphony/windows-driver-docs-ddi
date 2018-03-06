---
UID: NF:video.VideoPortReleaseSpinLockFromDpcLevel
title: VideoPortReleaseSpinLockFromDpcLevel function
author: windows-driver-content
description: The VideoPortReleaseSpinLockFromDpcLevel function releases the spin lock obtained by a previous call to VideoPortAcquireSpinLockAtDpcLevel.
old-location: display\videoportreleasespinlockfromdpclevel.htm
old-project: display
ms.assetid: 375158e7-3fb5-4e49-a7cf-ee9a1e5c07ca
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortReleaseSpinLockFromDpcLevel, VideoPortReleaseSpinLockFromDpcLevel function [Display Devices], VideoPort_Functions_2c3a3aa1-4ef4-4b7f-8cdf-b658a1128c35.xml, display.videoportreleasespinlockfromdpclevel, video/VideoPortReleaseSpinLockFromDpcLevel
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortReleaseSpinLockFromDpcLevel
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortReleaseSpinLockFromDpcLevel function
The <b>VideoPortReleaseSpinLockFromDpcLevel</b> function releases the spin lock obtained by a previous call to <a href="..\video\nf-video-videoportacquirespinlockatdpclevel.md">VideoPortAcquireSpinLockAtDpcLevel</a>.

## Syntax

````
VOID VideoPortReleaseSpinLockFromDpcLevel(
  _In_    PVOID      HwDeviceExtension,
  _Inout_ PSPIN_LOCK SpinLock
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`Arg1`




## Return Value

None

## Remarks

Miniport drivers call <b>VideoPortReleaseSpinLockFromDpcLevel</b> to release a spin lock acquired by calling <a href="..\video\nf-video-videoportacquirespinlockatdpclevel.md">VideoPortAcquireSpinLockAtDpcLevel</a>.

It is an error to call <b>VideoPortReleaseSpinLockFromDpcLevel</b> if the given spin lock was acquired by calling <a href="..\video\nf-video-videoportacquirespinlock.md">VideoPortAcquireSpinLock</a> because the caller's original IRQL is not restored, which can cause deadlocks or fatal page faults.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="..\video\nf-video-videoportacquirespinlockatdpclevel.md">VideoPortAcquireSpinLockAtDpcLevel</a>



<a href="..\video\nf-video-videoportacquirespinlock.md">VideoPortAcquireSpinLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortReleaseSpinLockFromDpcLevel function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>