---
UID: NF:video.VideoPortWriteRegisterUchar
title: VideoPortWriteRegisterUchar function
author: windows-driver-content
description: The VideoPortWriteRegisterUchar function writes a byte to a mapped register.
old-location: display\videoportwriteregisteruchar.htm
old-project: display
ms.assetid: 259d01a5-d975-48f9-b0cf-4596d12046bc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortWriteRegisterUchar, VideoPortWriteRegisterUchar function [Display Devices], VideoPort_Functions_b06fef25-2c8e-457f-9f6a-0f58573ac860.xml, display.videoportwriteregisteruchar, video/VideoPortWriteRegisterUchar
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
-	VideoPortWriteRegisterUchar
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortWriteRegisterUchar function
The <b>VideoPortWriteRegisterUchar</b> function writes a byte to a mapped register.

## Syntax

```
VIDEOPORT_API VOID VideoPortWriteRegisterUchar(
  PUCHAR Register,
  UCHAR  Value
);
```

## Parameters

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.

`Value`

Specifies a byte to be transferred to the adapter.


## Return Value

None

## Remarks

A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWriteRegisterUchar</b>.

Callers of <b>VideoPortWriteRegisterUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Register</i> parameter is resident, mapped device memory.

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