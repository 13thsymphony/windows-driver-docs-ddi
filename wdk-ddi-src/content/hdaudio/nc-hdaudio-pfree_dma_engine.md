---
UID: NC:hdaudio.PFREE_DMA_ENGINE
title: PFREE_DMA_ENGINE
author: windows-driver-content
description: The FreeDmaEngine routine frees a DMA engine that was previously allocated by a call to AllocateCaptureDmaEngine or AllocateRenderDmaEngine.The function pointer type for a FreeDmaEngine routine is defined as follows.
old-location: audio\freedmaengine.htm
old-project: audio
ms.assetid: 3f068ac0-2b18-4242-86de-7044ce558788
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FreeDmaEngine, FreeDmaEngine callback function [Audio Devices], PFREE_DMA_ENGINE, aud-prop2_98407bc5-c9ae-499f-92b4-afd8c797dc1d.xml, audio.freedmaengine, hdaudio/FreeDmaEngine
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	hdaudio.h
api_name:
-	FreeDmaEngine
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---


# PFREE_DMA_ENGINE callback function
The <code>FreeDmaEngine</code> routine frees a DMA engine that was previously allocated by a call to <b>AllocateCaptureDmaEngine</b> or <b>AllocateRenderDmaEngine</b>.

The function pointer type for a <code>FreeDmaEngine</code> routine is defined as follows.

## Syntax

```
PFREE_DMA_ENGINE PfreeDmaEngine;

NTSTATUS PfreeDmaEngine(
  PVOID _context,
  HANDLE Handle
)
{...}
```

## Parameters

`_context`

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a><u>, the </u><a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a> or <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.

`Handle`

Handle identifying the DMA engine. This handle value was obtained from a previous call to <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>.


## Return Value

<code>FreeDmaEngine</code> returns STATUS_SUCCESS if the call succeeds in freeing the DMA engine. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the <i>handle</i> parameter value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the stream is not in the reset state or that a buffer is still allocated for the DMA engine.

</td>
</tr>
</table>

## Remarks

This routine frees a DMA engine that was previously reserved by a call to the <b>AllocateCaptureDmaEngine</b> or <b>AllocateRenderDmaEngine</b> routine.

This routine fails and returns error code STATUS_INVALID_DEVICE_REQUEST in either of the following circumstances:

<ul>
<li>
Any previously allocated DMA buffer has not been freed (by calling <a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a> or <a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a>).

</li>
<li>
The stream is in a state other than reset.

</li>
</ul>
An audio driver calls this routine to close the pin (and destroy the stream).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hdaudio.h (include Hdaudio.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a>