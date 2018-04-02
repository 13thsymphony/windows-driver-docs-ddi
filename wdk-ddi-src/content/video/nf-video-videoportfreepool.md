---
UID: NF:video.VideoPortFreePool
title: VideoPortFreePool function
author: windows-driver-content
description: The VideoPortFreePool function deallocates a block of pool memory previously allocated by VideoPortAllocatePool.
old-location: display\videoportfreepool.htm
old-project: display
ms.assetid: 84e4f178-87d3-4f40-b4fc-7959818305fd
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortFreePool, VideoPortFreePool function [Display Devices], VideoPort_Functions_a2b1e2c4-9f8d-455b-8484-c51e0669d526.xml, display.videoportfreepool, video/VideoPortFreePool
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortFreePool
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortFreePool function
The <b>VideoPortFreePool</b> function deallocates a block of pool memory previously allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570180">VideoPortAllocatePool</a>.

## Syntax

```
VIDEOPORT_API VOID VideoPortFreePool(
  IN PVOID HwDeviceExtension,
  IN PVOID Ptr
);
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`Ptr`

Pointer to the first byte of the memory to be freed.


## Return Value

None

## Remarks

<b>VideoPortFreePool</b> is intended to replace <b>VideoPortReleaseBuffer</b>, which is obsolete.

Callers of <b>VideoPortFreePool</b> must be running at IRQL &lt;= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must have specified a <b>VpNonPaged </b><i>XxxPoolType</i> when the memory was allocated. Otherwise, the caller must be running at IRQL &lt; DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | See Remarks section. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570178">VideoPortAllocateCommonBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570180">VideoPortAllocatePool</a>