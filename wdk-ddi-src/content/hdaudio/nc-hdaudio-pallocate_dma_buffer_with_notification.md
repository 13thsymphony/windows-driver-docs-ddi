---
UID: NC:hdaudio.PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION
title: PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION
author: windows-driver-content
description: The AllocateDmaBufferWithNotification routine allocates a data buffer in system memory for a DMA engine.The function pointer type for an AllocateDmaBufferWithNotification routine is defined as follows.
old-location: audio\allocatedmabufferwithnotification.htm
old-project: audio
ms.assetid: c74b5969-35d4-45db-b631-31e00572107d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.allocatedmabufferwithnotification, AllocateDmaBufferWithNotification callback function [Audio Devices], AllocateDmaBufferWithNotification, PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION, PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION, hdaudio/AllocateDmaBufferWithNotification, aud-prop2_37aa129c-f389-402a-ba68-8dedb9ce6b6b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Hdaudio.h
apiname:
-	AllocateDmaBufferWithNotification
product: Windows
targetos: Windows
req.typenames: "*PSM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT"
---


# PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION callback function
The <code>AllocateDmaBufferWithNotification</code> routine allocates a data buffer in system memory for a DMA engine.

The function pointer type for an <code>AllocateDmaBufferWithNotification</code> routine is defined as follows.

## Syntax

```
PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION PallocateDmaBufferWithNotification;

NTSTATUS PallocateDmaBufferWithNotification(
  PVOID _context,
  HANDLE Handle,
  ULONG NotificationCount,
  SIZE_T RequestedBufferSize,
  PMDL *BufferMdl,
  PSIZE_T AllocatedBufferSize,
  PSIZE_T OffsetFromFirstPage,
  PUCHAR StreamId,
  PULONG FifoSize
)
{...}
```

## Parameters

`_context`

Specifies the context value from the Context member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a> structure.

`Handle`



`NotificationCount`



`RequestedBufferSize`



`*BufferMdl`



`AllocatedBufferSize`



`OffsetFromFirstPage`



`StreamId`



`FifoSize`




## Return Value

The <code>AllocateDmaBufferWithNotification</code> routine returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return error codes.
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
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the buffer allocation has failed.

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
Indicates that the stream is not in the reset state or that a buffer is already allocated for the DMA engine and has not yet been freed.

</td>
</tr>
</table>

## Remarks

The <code>AllocateDmaBufferWithNotification</code> routine is used together with the <a href="..\hdaudio\nc-hdaudio-pfree_dma_buffer_with_notification.md">FreeDmaBufferWithNotification</a> routine. These two routines are available only in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI. Unlike <a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>, which configures the DMA engine to use a previously allocated DMA buffer, <code>AllocateDmaBufferWithNotification</code> allocates a DMA buffer and also configures the DMA engine to use the buffer.

If the DMA engine cannot use a buffer of the size that is requested in parameter <i>requestedBufferSize</i>, the routine allocates a buffer that is as close as possible to the requested size.

The function driver for an audio or modem codec is responsible for programming the codec to manage the data transfers and to recognize the stream identifier.

<code>AllocateDmaBufferWithNotification</code> outputs an MDL that lists the physical memory pages that contain the buffer. The buffer base address coincides with the start of the first physical page in the list.

During the lifetime of a DMA engine handle, <code>AllocateDmaBufferWithNotification</code> can be called successively to allocate new DMA buffers. However, before calling <code>AllocateDmaBufferWithNotification</code>, any previously allocated DMA buffer must first be freed by calling FreeDmaBufferWithNotification.

During calls to <code>AllocateDmaBufferWithNotification</code> and <b>FreeDmaBufferWithNotification</b>, the DMA engine must be in the reset stream state. The DMA engine is in the reset stream state immediately following the call to <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>. To change the DMA engine to the run state, call <a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a>.

The FIFO size is the maximum number of bytes that the DMA engine can hold in its internal buffer. Depending on the hardware implementation, a DMA engine's FIFO size can either be static or vary dynamically with changes in the stream format. For more information about the FIFO size, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel High Definition Audio Specification</a>.

In Windows Vista and later versions of Windows, a WaveRT miniport driver calls this routine when it receives the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a> property request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows. Available in Windows Vista and later versions of Windows. |
| **Target Platform** | Desktop |
| **Header** | hdaudio.h (include Hdaudio.h) |
| **IRQL** | PASSIVE_LEVEL. |

## See Also

<a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>

<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>

<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>

<a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>