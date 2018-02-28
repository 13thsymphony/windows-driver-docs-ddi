---
UID: NF:video.VideoPortCompleteDma
title: VideoPortCompleteDma function
author: windows-driver-content
description: The VideoPortCompleteDma function flushes any data remaining in a bus-master adapter's internal cache at the end of a DMA transfer operation, and then frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA operations.
old-location: display\videoportcompletedma.htm
old-project: display
ms.assetid: 8af5a397-7945-4f72-a253-04d227bf3ca1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: VideoPortCompleteDma, VideoPortCompleteDma function [Display Devices], VideoPort_Functions_1ee3a02f-e0bb-4230-8161-957ceba37206.xml, display.videoportcompletedma, video/VideoPortCompleteDma
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortCompleteDma
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortCompleteDma function
The <b>VideoPortCompleteDma</b> function flushes any data remaining in a bus-master adapter's internal cache at the end of a DMA transfer operation, and then frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA operations.

## Syntax

````
VP_STATUS VideoPortCompleteDma(
  _In_ PVOID                   HwDeviceExtension,
  _In_ PVP_DMA_ADAPTER         VpDmaAdapter,
  _In_ PVP_SCATTER_GATHER_LIST VpScatterGather,
  _In_ BOOLEAN                 WriteToDevice
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`VpDmaAdapter`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This structure was returned by a call to <a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>.

`VpScatterGather`

Pointer to the <a href="..\video\ns-video-_vp_scatter_gather_list.md">VP_SCATTER_GATHER_LIST</a> structure previously passed to the miniport driver callback routine, <a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a>.

`WriteToDevice`

Specifies the direction of the DMA transfer. A value of <b>TRUE</b> denotes a transfer from the buffer to the device, and a value of <b>FALSE</b> denotes a transfer from the device to the buffer.


## Return Value

<b>VideoPortCompleteDma</b> returns NO_ERROR.

## Remarks

The video miniport driver should call <b>VideoPortCompleteDma</b> immediately to free up system resources after a DMA transfer has been completed. 

It is important to note that the scatter/gather list built by <b>VideoPortStartDma</b> becomes invalid when <b>VideoPortCompleteDma</b> is called..

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\video\ns-video-_vp_scatter_gather_list.md">VP_SCATTER_GATHER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a>



<a href="..\video\nf-video-videoportstartdma.md">VideoPortStartDma</a>



<a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortCompleteDma function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>