---
UID: NC:hdaudio.PSETUP_DMA_ENGINE_WITH_BDL
title: PSETUP_DMA_ENGINE_WITH_BDL
author: windows-driver-content
description: The SetupDmaEngineWithBdl routine sets up a DMA engine to use a caller-allocated DMA buffer.The function pointer type for a SetupDmaEngineWithBdl routine is defined as follows.
old-location: audio\setupdmaenginewithbdl.htm
old-project: audio
ms.assetid: 2760579b-9922-4709-a049-a73f3abd5043
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PSETUP_DMA_ENGINE_WITH_BDL, SetupDmaEngineWithBdl, SetupDmaEngineWithBdl callback function [Audio Devices], aud-prop2_7d264dff-4f47-4a5a-a587-636c57a12a9d.xml, audio.setupdmaenginewithbdl, hdaudio/SetupDmaEngineWithBdl
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
-	SetupDmaEngineWithBdl
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---


# PSETUP_DMA_ENGINE_WITH_BDL callback function
The <i>SetupDmaEngineWithBdl</i> routine sets up a DMA engine to use a caller-allocated DMA buffer.

The function pointer type for a <i>SetupDmaEngineWithBdl</i> routine is defined as follows.

## Syntax

```
PSETUP_DMA_ENGINE_WITH_BDL PsetupDmaEngineWithBdl;

NTSTATUS PsetupDmaEngineWithBdl(
  PVOID _context,
  HANDLE Handle,
  ULONG BufferLength,
  ULONG Lvi,
  PHDAUDIO_BDL_ISR Isr,
  PVOID Context,
  PUCHAR StreamId,
  PULONG FifoSize
)
{...}
```

## Parameters

`_context`

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.

`Handle`

Handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>.

`BufferLength`



`Lvi`

Specifies the last valid index (LVI). This parameter contains the index for the last valid buffer descriptor in the BDL. After the DMA engine processes this descriptor, it wraps back to the first descriptor in the list and continues processing. If the BDL contains <i>n</i> descriptors, they are numbered 0 to <i>n</i>-1. The <i>lvi</i> value must be at least 1; in other words, the BDL must contain at least two valid entries before the DMA engine can begin operation.

`Isr`

Function pointer to the caller's ISR. If the caller sets the interrupt-on-completion (IOC) bit in one or more of the buffer descriptors in the BDL, the HD Audio bus driver calls the ISR each time an IOC interrupt occurs on the stream. This parameter is a function pointer of type HDAUDIO_BDL_ISR, which is defined in the following Remarks section.

`Context`



`StreamId`

Retrieves the stream identifier. This parameter points to a caller-allocated UCHAR variable into which the routine writes the stream identifier that it assigns to the stream.

`FifoSize`

Retrieves the DMA engine's FIFO size in bytes. This parameter points to a caller-allocated UINT variable into which the routine writes the FIFO size.


## Return Value

<i>SetupDmaEngineWithBdl</i> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.

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
Indicates that the <i>handle</i> parameter value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the parameter values is incorrect (bad pointer or invalid stream format).

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
Indicates that the DMA device or DMA buffer is not allocated or the stream is not in the Reset state.

</td>
</tr>
</table>

## Remarks

The <i>SetupDmaEngineWithBdl</i> routine is used in conjunction with the <a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a> and <a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a> routines. These three routines are available only in the HDAUDIO_BUS_INTERFACE_BDL version of the HD Audio DDI. This DDI does not include the <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a> and <a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a> routines, which are never used in conjunction with <b>AllocateContiguousDmaBuffer</b>, <i>SetupDmaEngineWithBdl</i>, and <b>FreeContiguousDmaBuffer</b>. Unlike <i>SetupDmaEngineWithBdl</i>, which configures the DMA engine to use a previously allocated DMA buffer, <b>AllocateDmaBuffer</b> both allocates a DMA buffer and configures the DMA engine to use the buffer.

The caller must call <a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a> to allocate storage in the system memory for both the DMA buffer and the BDL that describes the physical memory pages in the buffer. The BDL entries must reside in memory that is physically contiguous. The BDL and buffer memory must meet the alignment requirements that are described in the <i>Intel High Definition Audio Specification</i> (see the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website).

Both the BDL and the buffer memory that it describes must remain valid during DMA operations. Following the call to <i>SetupDmaEngineWithBdl</i>, the BDL and buffer memory must remain valid as long as the DMA engine continues to use the buffer. The DMA engine uses the buffer until the function driver replaces the buffer by calling <i>SetupDmaEngineWithBdl</i> again or frees the DMA engine by calling <a href="..\hdaudio\nc-hdaudio-pfree_dma_engine.md">FreeDmaEngine</a>. The function driver is responsible for calling <a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a> to free the buffer and BDL when they are no longer required.

When allocating memory for the buffer, the caller must satisfy all hardware constraints for the address, length, and alignment of the physically contiguous blocks of memory that the BDL specifies. Thus, only clients with significant knowledge of the bus controller and system hardware should use the <i>SetupDmaEngineWithBdl</i> routine.

Before calling <i>SetupDmaEngineWithBdl</i> to configure a DMA engine, the client must call <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a> to allocate the DMA engine. The handle parameter is the value obtained from the preceding call to Allocate <i>Xxx</i>DmaEngine.

The caller is responsible for programming the codec to manage the data transfers and to recognize the stream identifier.

A WDM audio driver calls this routine at pin-creation time during execution of its <b>NewStream</b> method (for example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a>).

Following the call to <i>SetupDmaEngineWithBdl</i>, the DMA engine is in the Reset state. To start the DMA engine, call <a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a>.

Parameter <i>isr</i> specifies the ISR that the HD Audio bus driver is to call each time an IOC interrupt occurs on the stream. This parameter is a function pointer of type HDAUDIO_BDL_ISR, which is defined as:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef void
  (*PHDAUDIO_BDL_ISR)
    (IN VOID *Context, IN ULONG InterruptBitMask);</pre>
</td>
</tr>
</table></span></div>
The HD Audio bus driver calls the ISR with the same context value that the client specified in the context parameter of the preceding <i>SetupDmaEngineWithBdl</i> call. The <i>interruptBitMask</i> parameter contains the bits from the HD Audio controller device's stream status register that indicate the reason for the interrupt. The following table shows the meaning of the individual bits in <i>interruptBitMask</i>.

<table>
<tr>
<th>Bit Numbers</th>
<th>Meaning</th>
</tr>
<tr>
<td>
31:5

</td>
<td>

        Unused.
       

</td>
</tr>
<tr>
<td>
4

</td>
<td>

        Descriptor Error (DESE). If an error occurs during the fetch of a buffer descriptor, then the HD Audio controller sets the DESE bit to 1.

</td>
</tr>
<tr>
<td>
3

</td>
<td>

        FIFO Error (FIFOE). If a FIFO error occurs (an overrun on an output stream or an underrun on an input stream), then the HD Audio controller sets the FIFOE bit to 1.

</td>
</tr>
<tr>
<td>
2

</td>
<td>

        Buffer Completion Interrupt Status (BCIS). If the IOC bit is set to 1 in the command byte of the buffer descriptor, then the HD Audio controller sets the BCIS bit to 1 after the last sample of a buffer is processed.

</td>
</tr>
<tr>
<td>
1:0

</td>
<td>

        Unused.
       

</td>
</tr>
</table>
 

The HD Audio bus driver sets the unused bits to zero. Instead of assuming that an IOC interrupt has occurred, the ISR must always check the <i>interruptBitMask</i> parameter to determine whether a stream error has occurred. For more information about the interrupt status bits shown in the preceding table, see the description of the stream status registers in the <i>Intel High Definition Audio Specification</i>.

The FIFO size is the maximum number of bytes that the DMA engine can hold in its internal buffer at any one time. Depending on the hardware implementation, a DMA engine's FIFO size can either be static or vary dynamically with changes in the stream format. For more information about the FIFO size, see the <i>Intel High Definition Audio Specification</i>.

The caller must allocate the buffer memory and BDL from the nonpaged pool.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hdaudio.h (include Hdaudio.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_buffer_descriptor.md">HDAUDIO_BUFFER_DESCRIPTOR</a>



<a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer.md">FreeDmaBuffer</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PSETUP_DMA_ENGINE_WITH_BDL callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>