---
UID: NF:video.VideoPortReadPortBufferUchar
title: VideoPortReadPortBufferUchar function
author: windows-driver-content
description: The VideoPortReadPortBufferUchar function reads a number of bytes from a mapped I/O port and writes them into a buffer.
old-location: display\videoportreadportbufferuchar.htm
old-project: display
ms.assetid: 7eda10df-56f8-4bb5-8f36-6246e51c1638
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortReadPortBufferUchar, VideoPortReadPortBufferUchar function [Display Devices], VideoPort_Functions_b3c67bc0-e12c-4625-bba6-d7fb64e0c824.xml, display.videoportreadportbufferuchar, video/VideoPortReadPortBufferUchar
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortReadPortBufferUchar
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortReadPortBufferUchar function
The <b>VideoPortReadPortBufferUchar</b> function reads a number of bytes from a mapped I/O port and writes them into a buffer.

## Syntax

```
VIDEOPORT_API VOID VideoPortReadPortBufferUchar(
  PUCHAR Port,
  PUCHAR Buffer,
  ULONG  Count
);
```

## Parameters

`Port`

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.

`Buffer`

Pointer to a buffer into which the UCHAR values are written.

`Count`

Specifies the number of bytes to be written to the buffer.


## Return Value

None

## Remarks

The buffer must be large enough to contain at least the specified number of bytes.

A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadPortBufferUchar</b>.

Callers of <b>VideoPortReadPortBufferUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Port</i> parameter is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | See Remarks section. |

## See Also

<a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a>



<a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>