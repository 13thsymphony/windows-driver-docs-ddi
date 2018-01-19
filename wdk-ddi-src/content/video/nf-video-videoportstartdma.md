---
UID : NF:video.VideoPortStartDma
title : VideoPortStartDma function
author : windows-driver-content
description : The VideoPortStartDma function prepares the system for a DMA operation.
old-location : display\videoportstartdma.htm
old-project : display
ms.assetid : cb78e871-6177-4141-b713-25a39c928701
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : VideoPortStartDma
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : video.h
req.include-header : Video.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : VideoPortStartDma
req.alt-loc : Videoprt.sys
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Videoprt.lib
req.dll : Videoprt.sys
req.irql : <=DISPATCH_LEVEL
req.typenames : VIDEO_PORT_SERVICES
req.product : Windows 10 or later.
---


# VideoPortStartDma function
The <b>VideoPortStartDma</b> function prepares the system for a DMA operation. As soon as the appropriate resource is available, <b>VideoPortStartDma</b> creates a scatter/gather list, initializes the system resources, and calls the video miniport driver-supplied <a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a> routine to carry out the DMA operation.

## Syntax

````
VP_STATUS VideoPortStartDma(
  _In_    PVOID           HwDeviceExtension,
  _In_    PVP_DMA_ADAPTER VpDmaAdapter,
  _In_    PVOID           Mdl,
  _In_    ULONG           Offset,
  _Inout_ PULONG          pLength,
  _In_    PEXECUTE_DMA    ExecuteDmaRoutine,
  _In_    PVOID           Context,
  _In_    BOOLEAN         WriteToDevice
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`VpDmaAdapter`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This structure is returned from a call to <a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>.

`Mdl`

Pointer to the <a href="wdkgloss.m#wdkgloss.mdl#wdkgloss.mdl"><i>MDL</i></a> that describes the buffer. This pointer is returned from a call to the video port driver's <a href="..\video\nf-video-videoportlockbuffer.md">VideoPortLockBuffer</a> function.

`Offset`

Specifies the byte offset in the buffer at which the DMA operation begins. The <i>Mdl</i> parameter describes this buffer.

`pLength`

Pointer to a variable that specifies the requested transfer size, in bytes, and that will receive the actual size to be transferred. The variable will be updated when either of the following events occurs: <b>VideoPortStartDma</b> returns or <a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a> is called. It is therefore safe to read this variable from within <i>HwVidExecuteDma</i> even before <b>VideoPortStartDma</b> returns.

`ExecuteDmaRoutine`

Pointer to a miniport driver-supplied <a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a> callback routine. <b>VideoPortStartDma</b> calls this routine to program the hardware registers and start the actual DMA operation.

`Context`

Pointer to the driver-determined context to be passed to the miniport driver's <i>HwVidExecuteDma</i> callback routine. Since the <i>HwVidExecuteDma</i> callback routine runs at DISPATCH_LEVEL, the data that <i>Context</i> points to should be in nonpaged memory.

`WriteToDevice`

Specifies the direction of the DMA transfer. A value of <b>TRUE</b> denotes a transfer from the buffer to the device, and a value of <b>FALSE</b> denotes a transfer from the device to the buffer.


## Return Value

<b>VideoPortStartDma</b> returns one of the following status codes:
<dl>
<dt><b>NO_ERROR</b></dt>
</dl>The operation was successfully carried out.
<dl>
<dt><b>ERROR_NOT_ENOUGH_MEMORY</b></dt>
</dl>There are not enough system resources for this operation.

## Remarks

To prepare for a DMA-transfer operation, <b>VideoPortStartDma</b>:

Flushes the memory region in the host processor's caches.

Builds a scatter/gather list.

Calls the video miniport driver's <a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a> callback.

It is possible that not all of the requested data has been transferred, since the actual amount of memory transferred is limited by the number of map registers available to the driver. Callers of this function should inspect the actual transfer size returned at <i>pLength</i> to determine whether additional data remains to be transferred. If so, the miniport driver should call <b>VideoPortStartDma</b> (and subsequently, <a href="..\video\nf-video-videoportcompletedma.md">VideoPortCompleteDma</a>) as many times as necessary to fulfill the entire transfer request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | video.h (include Video.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportcompletedma.md">VideoPortCompleteDma</a>
</dt>
<dt>
<a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortStartDma function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>