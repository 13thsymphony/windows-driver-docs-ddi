---
UID: NF:video.VideoPortFreeCommonBuffer
title: VideoPortFreeCommonBuffer function
author: windows-driver-content
description: The VideoPortFreeCommonBuffer function is obsolete and is supported only for backward compatibility with existing drivers.
old-location: display\videoportfreecommonbuffer.htm
old-project: display
ms.assetid: 8725868e-00bc-45fe-ab9d-c192abd1a059
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortFreeCommonBuffer, VideoPortFreeCommonBuffer function [Display Devices], VideoPort_Functions_0f1acebf-0fdf-4152-ad91-2cafed40296c.xml, display.videoportfreecommonbuffer, video/VideoPortFreeCommonBuffer
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortFreeCommonBuffer
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortFreeCommonBuffer function
The <b>VideoPortFreeCommonBuffer</b> function is <b>obsolete</b> and is supported only for backward compatibility with existing drivers. In its place, driver writers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff570355">VideoPortReleaseCommonBuffer</a>.

<b>VideoPortFreeCommonBuffer</b> deallocates system memory that was allocated by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570308">VideoPortGetCommonBuffer</a>.

## Syntax

```
VIDEOPORT_API VOID VideoPortFreeCommonBuffer(
  IN PVOID            HwDeviceExtension,
  IN ULONG            Length,
  IN PVOID            VirtualAddress,
  IN PHYSICAL_ADDRESS LogicalAddress,
  IN BOOLEAN          CacheEnabled
);
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`Length`

Specifies the number of bytes of memory to be freed.

`VirtualAddress`

Pointer to the corresponding virtual address of the allocated memory range.

`LogicalAddress`

Specifies the logical address of the buffer to be freed.

`CacheEnabled`

Indicates whether the allocated memory is cached.


## Return Value

None

## Remarks

Except for <a href="https://msdn.microsoft.com/c8329d26-fb6f-46f1-aacd-ba78ee4ea5d5">VideoPortGetCommonBuffer's </a><i>Alignment</i> parameter, all of the parameters used in a call to <b>VideoPortFreeCommonBuffer</b> must have the same values as those used in the previous call to <b>VideoPortGetCommonBuffer</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570308">VideoPortGetCommonBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570355">VideoPortReleaseCommonBuffer</a>