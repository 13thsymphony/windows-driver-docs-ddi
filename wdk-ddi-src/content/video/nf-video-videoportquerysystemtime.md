---
UID: NF:video.VideoPortQuerySystemTime
title: VideoPortQuerySystemTime function
author: windows-driver-content
description: The VideoPortQuerySystemTime function obtains the current system time.
old-location: display\videoportquerysystemtime.htm
old-project: display
ms.assetid: d9b54710-6ad2-4959-9172-76c90468d343
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortQuerySystemTime, VideoPortQuerySystemTime function [Display Devices], VideoPort_Functions_18c4e015-b294-40e0-8aef-7642d3a9cb27.xml, display.videoportquerysystemtime, video/VideoPortQuerySystemTime
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortQuerySystemTime
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortQuerySystemTime function
The <b>VideoPortQuerySystemTime</b> function obtains the current system time.

## Syntax

```
VIDEOPORT_API VOID VideoPortQuerySystemTime(
  OUT PLARGE_INTEGER CurrentTime
);
```

## Parameters

`CurrentTime`

Pointer to a memory location that will receive the current system time.


## Return Value

None

## Remarks

System time is a count of 100-nanosecond intervals since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone. To adjust this value for the local time zone use <a href="https://msdn.microsoft.com/library/windows/hardware/ff545622">ExSystemTimeToLocalTime</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570336">VideoPortQueryPerformanceCounter</a>