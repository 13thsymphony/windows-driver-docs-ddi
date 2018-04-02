---
UID: NF:video.VideoPortWritePortUchar
title: VideoPortWritePortUchar function
author: windows-driver-content
description: The VideoPortWritePortUchar function writes a byte to a mapped I/O port.
old-location: display\videoportwriteportuchar.htm
old-project: display
ms.assetid: 0f05f765-ca59-4a92-91a0-f1123dd9cd6f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortWritePortUchar, VideoPortWritePortUchar function [Display Devices], VideoPort_Functions_cfd3f257-e96f-4f75-a335-6b78aaa47c70.xml, display.videoportwriteportuchar, video/VideoPortWritePortUchar
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
-	VideoPortWritePortUchar
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortWritePortUchar function
The <b>VideoPortWritePortUchar</b> function writes a byte to a mapped I/O port.

## Syntax

```
VIDEOPORT_API VOID VideoPortWritePortUchar(
  PUCHAR Port,
  UCHAR  Value
);
```

## Parameters

`Port`

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.

`Value`

Specifies a byte to be transferred to the adapter.


## Return Value

None

## Remarks

A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWritePortUchar</b>.

Callers of <b>VideoPortWritePortUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Port</i> parameter is resident, mapped device memory.

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