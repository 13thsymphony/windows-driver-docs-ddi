---
UID : NC:hdaudio.PALLOCATE_CONTIGUOUS_DMA_BUFFER
title : PALLOCATE_CONTIGUOUS_DMA_BUFFER
author : windows-driver-content
description : The AllocateContiguousDmaBuffer routine allocates a DMA buffer that consists of a single, contiguous block of physical memory.The function pointer type for an AllocateContiguousDmaBuffer routine is defined as:
old-location : audio\allocatecontiguousdmabuffer.htm
old-project : audio
ms.assetid : 4538ce8e-fccd-4862-b226-a99fe578a5fd
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audio.allocatecontiguousdmabuffer, AllocateContiguousDmaBuffer callback function [Audio Devices], AllocateContiguousDmaBuffer, PALLOCATE_CONTIGUOUS_DMA_BUFFER, PALLOCATE_CONTIGUOUS_DMA_BUFFER, hdaudio/AllocateContiguousDmaBuffer, aud-prop2_c9f2fa85-0967-4793-9092-9f95986c2126.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : hdaudio.h
req.include-header : Hdaudio.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---


# PALLOCATE_CONTIGUOUS_DMA_BUFFER callback function
The <code>AllocateContiguousDmaBuffer</code> routine allocates a DMA buffer that consists of a single, contiguous block of physical memory.

The function pointer type for an <code>AllocateContiguousDmaBuffer</code> routine is defined as:

## Syntax

```
PALLOCATE_CONTIGUOUS_DMA_BUFFER PallocateContiguousDmaBuffer;

NTSTATUS PallocateContiguousDmaBuffer(
  PVOID _context,
  HANDLE Handle,
  ULONG RequestedBufferSize,
  PVOID *DataBuffer,
  PHDAUDIO_BUFFER_DESCRIPTOR *BdlBuffer
)
{...}
```

## Parameters

`_context`

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.

`Handle`



`RequestedBufferSize`



`*DataBuffer`



`*BdlBuffer`




## Return Value

<code>AllocateContiguousDmaBuffer</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.
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
Indicates that the caller is running at an interrupt request level (IRQL) that is too high.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that buffer allocation failed.

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the parameter values is incorrect (bad pointer).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the hardware programming timed out. If this occurs, the hardware might be in a compromised state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the stream is not in the reset state or that a buffer is already allocated for the DMA engine.

</td>
</tr>
</table>

## Remarks

The <code>AllocateContiguousDmaBuffer</code> routine is used in conjunction with the <a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a> and <a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a> routines. These three routines are available only in the HDAUDIO_BUS_INTERFACE_BDL version of the HD Audio DDI. This DDI does not include the <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a> and <a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a> routines, which are never used in conjunction with <code>AllocateContiguousDmaBuffer</code>, <b>SetupDmaEngineWithBdl</b>, and <b>FreeContiguousDmaBuffer</b>. Unlike <b>SetupDmaEngineWithBdl</b>, which configures the DMA engine to use a previously allocated DMA buffer, <code>AllocateDmaBuffer</code> both allocates a DMA buffer and configures the DMA engine to use the buffer. For more information, see <a href="https://msdn.microsoft.com/e24071d3-9021-40c0-907a-91ada8a1306b">Differences between the Two DDI Versions</a>.

<code>AllocateContiguousDmaBuffer</code> allocates a data buffer for the specified DMA engine. It also allocates a page of memory for the BDL. Depending on the host processor architecture, a typical page size might be 4,096 or 8,192 bytes. The data buffer consists of a single, contiguous block of physical memory.

The handle parameter specifies the DMA engine that is to use the data buffer and BDL. The routine allocates storage that meets the DMA engine's size, alignment, and position requirements.

The storage that the routine allocates for the data buffer and BDL is uninitialized. The function driver is responsible for filling in the BDL before submitting it to the <b>SetupDmaEngineWithBdl</b> routine. The function driver is also responsible for programming the codec to manage the data transfers and to recognize the stream identifier.

To generate IOC interrupts at precise intervals, the function driver might be required to divide the data buffer allocation into several fragments of a particular size. Each fragment is described by a BDL entry. The fragment size can be adjusted to tune the interrupt rate. According to the Intel High Definition Audio Specification (see the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website), each fragment must begin on a 128-byte boundary, although no such alignment requirement applies to the length of the fragment. Thus, a gap might exist between the end of one fragment and the beginning of the next. When calling <b>SetupDmaEngineWithBdl</b>, the function driver must specify a value for the <i>bufferSize</i> parameter that represents the sum of the sizes of the individual fragments that the BDL entries describe. This size will be less than or equal to the number of bytes specified in the <code>AllocateContiguousDmaBuffer</code> routine's <i>requestedBufferSize</i> parameter.

During the lifetime of a DMA engine handle, <code>AllocateContiguousDmaBuffer</code> can be called successively to allocate new DMA buffers. However, before calling <code>AllocateContiguousDmaBuffer</code>, any previously allocated DMA buffer must first be freed by calling <b>FreeContiguousDmaBuffer</b>.

During calls to <code>AllocateContiguousDmaBuffer</code>, <b>SetupDmaEngineWithBdl</b>, and <b>FreeContiguousDmaBuffer</b>, the DMA engine must be in the reset stream state. The DMA engine is in the reset state immediately following the call to Allocate<i>Xxx</i>DmaEngine. To change the DMA engine to the run state, call <a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a>.

This routine fails and returns error code STATUS_INVALID_DEVICE_REQUEST in either of the following circumstances:
<ul>
<li>
Any previously allocated DMA buffer has not been freed (by calling <b>FreeContiguousDmaBuffer</b>).

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

<a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>

<a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a>

<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a>

<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>

<a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a>

<a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a>

<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PALLOCATE_CONTIGUOUS_DMA_BUFFER callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>