---
UID: NF:video.VideoPortPutDmaAdapter
title: VideoPortPutDmaAdapter function
author: windows-driver-content
description: The VideoPortPutDmaAdapter function frees a VP_DMA_ADAPTER structure that was previously allocated by a call to VideoPortGetDmaAdapter.
old-location: display\videoportputdmaadapter.htm
old-project: display
ms.assetid: 80f1f1bd-57da-46b2-9967-9ba4b08ea057
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortPutDmaAdapter, VideoPortPutDmaAdapter function [Display Devices], VideoPort_Functions_3de2fb91-53a9-4a1d-9dcd-91e3c0d645ab.xml, display.videoportputdmaadapter, video/VideoPortPutDmaAdapter
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortPutDmaAdapter
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortPutDmaAdapter function
The <b>VideoPortPutDmaAdapter</b> function frees a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that was previously allocated by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570312">VideoPortGetDmaAdapter</a>.

## Syntax

```
VIDEOPORT_API VOID VideoPortPutDmaAdapter(
  IN PVOID           HwDeviceExtension,
  IN PVP_DMA_ADAPTER VpDmaAdapter
);
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`VpDmaAdapter`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter.


## Return Value

None

## Remarks

A miniport driver should call this function only if it will not use the same VP_DMA_ADAPTER structure again.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570312">VideoPortGetDmaAdapter</a>