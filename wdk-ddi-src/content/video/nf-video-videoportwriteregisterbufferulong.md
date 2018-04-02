---
UID: NF:video.VideoPortWriteRegisterBufferUlong
title: VideoPortWriteRegisterBufferUlong function
author: windows-driver-content
description: The VideoPortWriteRegisterBufferUlong function writes a number of ULONG values to a mapped register.
old-location: display\videoportwriteregisterbufferulong.htm
old-project: display
ms.assetid: 48322143-8c95-4ffa-ac7a-597ed5fb066c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortWriteRegisterBufferUlong, VideoPortWriteRegisterBufferUlong function [Display Devices], VideoPort_Functions_c9709e69-cf6e-4772-8889-0c37f79c0b22.xml, display.videoportwriteregisterbufferulong, video/VideoPortWriteRegisterBufferUlong
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
-	VideoPortWriteRegisterBufferUlong
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortWriteRegisterBufferUlong function
The <b>VideoPortWriteRegisterBufferUlong</b> function writes a number of ULONG values to a mapped register.

## Syntax

```
VIDEOPORT_API VOID VideoPortWriteRegisterBufferUlong(
  PULONG Register,
  PULONG Buffer,
  ULONG  Count
);
```

## Parameters

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.

`Buffer`

Pointer to a buffer containing the ULONG values to be written.

`Count`

Specifies the number of ULONG values to be transferred to the adapter.


## Return Value

None

## Remarks

A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWriteRegisterBufferUlong</b>.

Callers of <b>VideoPortWriteRegisterBufferUlong</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Register</i> parameter is resident, mapped device memory.

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