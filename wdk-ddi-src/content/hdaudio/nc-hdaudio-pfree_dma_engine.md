---
UID: NC.hdaudio.PFREE_DMA_ENGINE
title: PFREE_DMA_ENGINE
author: windows-driver-content
description: The FreeDmaEngine routine frees a DMA engine that was previously allocated by a call to AllocateCaptureDmaEngine or AllocateRenderDmaEngine.The function pointer type for a FreeDmaEngine routine is defined as:
old-location: audio\freedmaengine.htm
old-project: audio
ms.assetid: 3f068ac0-2b18-4242-86de-7044ce558788
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SM_SetRNIDMgmtInfo_OUT, PSM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
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
req.alt-api: FreeDmaEngine
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
req.irql: <=DISPATCH_LEVEL
---

# PFREE_DMA_ENGINE callback



## -description
The <code>FreeDmaEngine</code> routine frees a DMA engine that was previously allocated by a call to <b>AllocateCaptureDmaEngine</b> or <b>AllocateRenderDmaEngine</b>.

The function pointer type for a <code>FreeDmaEngine</code> routine is defined as:



## -prototype

````
PFREE_DMA_ENGINE FreeDmaEngine;

NTSTATUS FreeDmaEngine(
  _In_ PVOID  context,
  _In_ HANDLE handle
)
{ ... }
````


## -parameters

### -param context [in]

Specifies the context value from the <b>Context</b> member of the <a href="audio.hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a><u>, the </u><a href="audio.hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a> or <a href="audio.hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


### -param handle [in]

Handle identifying the DMA engine. This handle value was obtained from a previous call to <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>.


## -returns
<code>FreeDmaEngine</code> returns STATUS_SUCCESS if the call succeeds in freeing the DMA engine. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>Indicates that the <i>handle</i> parameter value is invalid.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>Indicates that the stream is not in the reset state or that a buffer is still allocated for the DMA engine.

 


## -remarks
This routine frees a DMA engine that was previously reserved by a call to the <b>AllocateCaptureDmaEngine</b> or <b>AllocateRenderDmaEngine</b> routine.

This routine fails and returns error code STATUS_INVALID_DEVICE_REQUEST in either of the following circumstances:

Any previously allocated DMA buffer has not been freed (by calling <a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a> or <a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a>).

The stream is in a state other than reset.

An audio driver calls this routine to close the pin (and destroy the stream).


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hdaudio.h (include Hdaudio.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="audio.hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>
</dt>
<dt>
<a href="audio.hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>
</dt>
<dt>
<a href="audio.hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PFREE_DMA_ENGINE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

