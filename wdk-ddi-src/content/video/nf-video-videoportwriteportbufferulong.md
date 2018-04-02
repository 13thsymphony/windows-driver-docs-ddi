---
UID: NF:video.VideoPortWritePortBufferUlong
title: VideoPortWritePortBufferUlong function
author: windows-driver-content
description: The VideoPortWritePortBufferUlong function writes a number of ULONG values to a mapped I/O port.
old-location: display\videoportwriteportbufferulong.htm
old-project: display
ms.assetid: 7b892bea-a21a-4bf3-863a-d56d919538aa
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortWritePortBufferUlong, VideoPortWritePortBufferUlong function [Display Devices], VideoPort_Functions_f8e5a168-7d9d-4478-b3e9-00053456506f.xml, display.videoportwriteportbufferulong, video/VideoPortWritePortBufferUlong
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortWritePortBufferUlong
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortWritePortBufferUlong function
The <b>VideoPortWritePortBufferUlong</b> function writes a number of ULONG values to a mapped I/O port.

## Syntax

```
VIDEOPORT_API VOID VideoPortWritePortBufferUlong(
  PULONG Port,
  PULONG Buffer,
  ULONG  Count
);
```

## Parameters

`Port`

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.

`Buffer`

Pointer to a buffer containing the ULONG values to be written.

`Count`

Specifies the number of ULONG values to be transferred to the adapter.


## Return Value

None

## Remarks

A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWritePortBufferUlong</b>.

Callers of <b>VideoPortWritePortBufferUlong</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Port</i> parameter is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | Any level (see Remarks section) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>