---
UID: NF:video.VideoPortReleaseSpinLock
title: VideoPortReleaseSpinLock function
author: windows-driver-content
description: The VideoPortReleaseSpinLock function releases ownership of a given spin lock and restores the original IRQL at which the caller was running.
old-location: display\videoportreleasespinlock.htm
old-project: display
ms.assetid: 8ce2006e-e66c-4b2d-8d26-2eba8d8e2864
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPort_Functions_43cceda5-f5eb-4567-97f5-d53d0bf93c0b.xml, display.videoportreleasespinlock, video/VideoPortReleaseSpinLock, VideoPortReleaseSpinLock function [Display Devices], VideoPortReleaseSpinLock
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
req.irql: DISPATCH_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortReleaseSpinLock
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortReleaseSpinLock function
The <b>VideoPortReleaseSpinLock</b> function releases ownership of a given spin lock and restores the original IRQL at which the caller was running.

## Syntax

````
VOID VideoPortReleaseSpinLock(
  _In_    PVOID      HwDeviceExtension,
  _Inout_ PSPIN_LOCK SpinLock,
  _In_    UCHAR      NewIrql
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`Arg1`



`NewIrql`

Specifies the IRQL to be restored.


## Return Value

None

## Remarks

This call is the inverse of <a href="..\video\nf-video-videoportacquirespinlock.md">VideoPortAcquireSpinLock</a>. The <i>NewIrql</i> value must be the same as the value pointed to by <i>OldIrql</i> when <b>VideoPortAcquireSpinLock </b>returned.

Callers of <b>VideoPortReleaseSpinLock</b> must be running at IRQL = DISPATCH_LEVEL. On return from this routine, IRQL is restored to the <i>NewIrql</i> value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | DISPATCH_LEVEL (see Remarks section) |

## See Also

<a href="..\video\nf-video-videoportacquirespinlock.md">VideoPortAcquireSpinLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortReleaseSpinLock function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>