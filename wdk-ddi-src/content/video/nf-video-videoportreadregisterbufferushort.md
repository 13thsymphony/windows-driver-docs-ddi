---
UID: NF:video.VideoPortReadRegisterBufferUshort
title: VideoPortReadRegisterBufferUshort function
author: windows-driver-content
description: The VideoPortReadRegisterBufferUshort function reads a number of USHORT values from a mapped device memory range and writes them into a buffer.
old-location: display\videoportreadregisterbufferushort.htm
old-project: display
ms.assetid: 5a8e0be5-8eed-47f1-88df-43f3776def7f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortReadRegisterBufferUshort, VideoPortReadRegisterBufferUshort function [Display Devices], VideoPort_Functions_f10955b1-ab90-46dc-8e53-1c395af6f0bc.xml, display.videoportreadregisterbufferushort, video/VideoPortReadRegisterBufferUshort
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
-	VideoPortReadRegisterBufferUshort
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortReadRegisterBufferUshort function
The <b>VideoPortReadRegisterBufferUshort</b> function reads a number of USHORT values from a mapped device memory range and writes them into a buffer.

## Syntax

```
VIDEOPORT_API VOID VideoPortReadRegisterBufferUshort(
  PUSHORT Register,
  PUSHORT Buffer,
  ULONG   Count
);
```

## Parameters

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.

`Buffer`

Pointer to a buffer into which the USHORT values are written.

`Count`

Specifies the number of USHORT values to be written to the buffer.


## Return Value

None

## Remarks

The buffer must be large enough to contain at least the specified number of USHORT values.

A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadRegisterBufferUshort</b>.

Callers of <b>VideoPortReadRegisterBufferUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Register</i> parameter is resident, mapped device memory.

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