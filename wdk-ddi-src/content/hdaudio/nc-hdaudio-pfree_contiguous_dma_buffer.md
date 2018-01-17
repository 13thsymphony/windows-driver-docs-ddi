---
UID: NC:hdaudio.PFREE_CONTIGUOUS_DMA_BUFFER
title: PFREE_CONTIGUOUS_DMA_BUFFER
author: windows-driver-content
description: The FreeContiguousDmaBuffer routine frees a DMA buffer and buffer descriptor list (BDL) that were allocated by a call to AllocateContiguousDmaBuffer.The function pointer type for a FreeContiguousDmaBuffer routine is defined as:
old-location: audio\freecontiguousdmabuffer.htm
old-project: audio
ms.assetid: 7aaf98cc-8a94-44e6-9fef-76e00db17405
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FreeContiguousDmaBuffer
req.alt-loc: hdaudio.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PSM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT
---

# PFREE_CONTIGUOUS_DMA_BUFFER callback



## -description
The <code>FreeContiguousDmaBuffer</code> routine frees a DMA buffer and buffer descriptor list (BDL) that were allocated by a call to <b>AllocateContiguousDmaBuffer</b>.

The function pointer type for a <code>FreeContiguousDmaBuffer</code> routine is defined as:



## -prototype

````
PFREE_CONTIGUOUS_DMA_BUFFER FreeContiguousDmaBuffer;

NTSTATUS FreeContiguousDmaBuffer(
  _In_ PVOID  context,
  _In_ HANDLE handle
)
{ ... }
````


## -parameters

### -param context [in]

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


### -param handle [in]

Handle identifying the DMA engine. This handle value was obtained from a previous call to <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>.


## -returns
<code>FreeContiguousDmaBuffer</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>Indicates that the caller is running at an IRQL that is too high.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>Indicates that the handle parameter value is invalid.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>Indicates that the stream is not in the reset state or that no buffer is currently allocated for the DMA engine.

 


## -remarks
The <code>FreeContiguousDmaBuffer</code> routine is used in conjunction with the <a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a> and <a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a> routines. These three routines are available only in the HDAUDIO_BUS_INTERFACE_BDL version of the HD Audio DDI. This DDI does not include the <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a> and <a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a> routines, which are never used in conjunction with <b>AllocateContiguousDmaBuffer</b>, <b>SetupDmaEngineWithBdl</b>, and <code>FreeContiguousDmaBuffer</code>. Unlike <b>SetupDmaEngineWithBdl</b>, which configures the DMA engine to use a previously allocated DMA buffer, <b>AllocateDmaBuffer</b> both allocates a DMA buffer and configures the DMA engine to use the buffer. For more information, see <a href="https://msdn.microsoft.com/e24071d3-9021-40c0-907a-91ada8a1306b">Differences between the Two DDI Versions</a>.

The routine fails and returns error code STATUS_INVALID_DEVICE_REQUEST in either of the following circumstances:

The client calls <code>FreeContiguousDmaBuffer</code> when no buffer is currently allocated for the DMA engine.

The stream is in a state other than reset.


## -see-also
<dl>
<dt>
<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PFREE_CONTIGUOUS_DMA_BUFFER callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

