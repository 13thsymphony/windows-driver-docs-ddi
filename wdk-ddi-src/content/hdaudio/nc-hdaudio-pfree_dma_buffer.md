---
UID: NC:hdaudio.PFREE_DMA_BUFFER
title: PFREE_DMA_BUFFER
author: windows-driver-content
description: The FreeDmaBuffer routine frees a DMA buffer that was previously allocated by a call to AllocateDmaBuffer.The function pointer type for a FreeDmaBuffer routine is defined as follows.
old-location: audio\freedmabuffer.htm
old-project: audio
ms.assetid: 658e32d2-40e2-4479-8212-df7140fe6b74
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FreeDmaBuffer, FreeDmaBuffer callback function [Audio Devices], PFREE_DMA_BUFFER, aud-prop2_22e95124-bf77-40d9-9ad7-4edc394818df.xml, audio.freedmabuffer, hdaudio/FreeDmaBuffer
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	hdaudio.h
api_name:
-	FreeDmaBuffer
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---


# PFREE_DMA_BUFFER callback function
The <code>FreeDmaBuffer</code> routine frees a DMA buffer that was previously allocated by a call to <b>AllocateDmaBuffer</b>.

The function pointer type for a <code>FreeDmaBuffer</code> routine is defined as follows.

## Syntax

```
PFREE_DMA_BUFFER PfreeDmaBuffer;

NTSTATUS PfreeDmaBuffer(
  PVOID _context,
  HANDLE Handle
)
{...}
```

## Parameters

`_context`

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a> or the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a> structure.

`Handle`

Handle identifying the DMA engine. This handle value was obtained from a previous call to <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>.


## Return Value

<code>FreeDmaBuffer</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the caller is running at an IRQL that is too high.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the handle parameter value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the stream is not in the reset state or that no buffer is currently allocated for the DMA engine.

</td>
</tr>
</table>

## Remarks

The <code>FreeDmaBuffer</code> routine is used in conjunction with the <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a> routine. These two routines are available only in the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI. This DDI does not include the <a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a>, <a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>, and <a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a> routines, which are never used in conjunction with <b>AllocateDmaBuffer</b> and <code>FreeDmaBuffer</code>. Unlike <b>SetupDmaEngineWithBdl</b>, which configures the DMA engine to use a previously allocated DMA buffer, <b>AllocateDmaBuffer</b> both allocates a DMA buffer and configures the DMA engine to use the buffer.

The routine fails and returns error code STATUS_INVALID_DEVICE_REQUEST in either of the following circumstances:

<ul>
<li>
The client calls <code>FreeDmaBuffer</code> when no buffer is currently allocated for the DMA engine.

</li>
<li>
The stream is in a state other than reset.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hdaudio.h (include Hdaudio.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>