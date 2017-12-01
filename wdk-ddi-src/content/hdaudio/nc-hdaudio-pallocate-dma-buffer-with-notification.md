---
UID: NC.hdaudio.PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION
title: PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION
author: windows-driver-content
description: The AllocateDmaBufferWithNotification routine allocates a data buffer in system memory for a DMA engine.The function pointer type for an AllocateDmaBufferWithNotification routine is defined as follows.
old-location: audio\allocatedmabufferwithnotification.htm
old-project: audio
ms.assetid: c74b5969-35d4-45db-b631-31e00572107d
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: SM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
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
req.alt-api: AllocateDmaBufferWithNotification
req.alt-loc: Hdaudio.h
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
req.iface: 
---

# PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION callback



## -description
<p>The <code>AllocateDmaBufferWithNotification</code> routine allocates a data buffer in system memory for a DMA engine.</p>
<p>The function pointer type for an <code>AllocateDmaBufferWithNotification</code> routine is defined as follows.</p>


## -prototype

````
PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION AllocateDmaBufferWithNotification;

NTSTATUS AllocateDmaBufferWithNotification(
  _In_  PVOID   context,
  _In_  HANDLE  handle,
  _In_  ULONG   notificationCount,
  _In_  SIZE_T  requestedBufferSize,
  _Out_ PMDL    *bufferMdl,
  _Out_ PSIZE_T allocatedBufferSize,
  _Out_ PUCHAR  streamID,
  _Out_ PULONG  fifoSize
)
{ ... }
````


## -parameters
<dl>

### -param <i>context</i> [in]

<dd>
<p>Specifies the context value from the Context member of the <a href="..\hdaudio\ns-hdaudio--hdaudio-bus-interface-v2.md">HDAUDIO_BUS_INTERFACE_V2</a> structure.</p>
</dd>

### -param <i>handle</i> [in]

<dd>
<p>A handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="..\hdaudio\nc-hdaudio-pallocate-capture-dma-engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate-render-dma-engine.md">AllocateRenderDmaEngine</a>.</p>
</dd>

### -param <i>notificationCount</i> [in]

<dd>
<p>Specifies the number of notifications that are needed, based on DMA progression through the audio buffer.  Currently, a value of 1 or 2 is supported.  When the value is 1, any registered notification events are signaled each time the cyclic audio buffer is completed and DMA wraps back to the beginning.  When the value is 2, any registered notification events are notified as DMA passes the midpoint of the audio buffer as well as at the end (or the wraparound point).</p>
</dd>

### -param <i>requestedBufferSize</i> [in]

<dd>
<p>Specifies the requested buffer size, in bytes.</p>
</dd>

### -param <i>bufferMdl</i> [out]

<dd>
<p>Retrieves the physical memory pages that contain the allocated buffer. This parameter points to a caller-allocated variable that is a pointer to a memory descriptor list (PMDL). This routine writes a pointer that describes the memory descriptor list buffer, to the PMDL variable.</p>
</dd>

### -param <i>allocatedBufferSize</i> [out]

<dd>
<p>Retrieves the allocated buffer size, in bytes. This parameter points to a caller-allocated SIZE_T variable into which the routine writes the size of the allocated buffer.</p>
</dd>

### -param <i>streamID</i> [out]

<dd>
<p>Retrieves the stream identifier. This parameter points to a caller-allocated UCHAR variable into which the routine writes the stream identifier that the routine assigns to the stream.</p>
</dd>

### -param <i>fifoSize</i> [out]

<dd>
<p>Retrieves the DMA engine's FIFO size, in bytes. This parameter points to a caller-allocated ULONG variable into which the routine writes the FIFO size.</p>
</dd>
</dl>

## -returns
<p>The <code>AllocateDmaBufferWithNotification</code> routine returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return error codes.</p><dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl><p>Indicates that the caller is running at an IRQL that is too high.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>Indicates that the buffer allocation has failed.</p><dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl><p>Indicates that the handle parameter value is invalid.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>Indicates that one of the parameter values is incorrect (bad pointer).</p><dl>
<dt><b>STATUS_DEVICE_NOT_READY</b></dt>
</dl><p>Indicates that the hardware programming timed out. If this occurs, the hardware might be in a compromised state.</p><dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl><p>Indicates that the stream is not in the reset state or that a buffer is already allocated for the DMA engine and has not yet been freed.</p>

<p> </p>

## -remarks
<p>The <code>AllocateDmaBufferWithNotification</code> routine is used together with the <a href="..\hdaudio\nc-hdaudio-pfree-dma-buffer-with-notification.md">FreeDmaBufferWithNotification</a> routine. These two routines are available only in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI. Unlike <a href="..\hdaudio\nc-hdaudio-psetup-dma-engine-with-bdl.md">SetupDmaEngineWithBdl</a>, which configures the DMA engine to use a previously allocated DMA buffer, <code>AllocateDmaBufferWithNotification</code> allocates a DMA buffer and also configures the DMA engine to use the buffer.</p>

<p>If the DMA engine cannot use a buffer of the size that is requested in parameter <i>requestedBufferSize</i>, the routine allocates a buffer that is as close as possible to the requested size.</p>

<p>The function driver for an audio or modem codec is responsible for programming the codec to manage the data transfers and to recognize the stream identifier.</p>

<p><code>AllocateDmaBufferWithNotification</code> outputs an MDL that lists the physical memory pages that contain the buffer. The buffer base address coincides with the start of the first physical page in the list.</p>

<p>During the lifetime of a DMA engine handle, <code>AllocateDmaBufferWithNotification</code> can be called successively to allocate new DMA buffers. However, before calling <code>AllocateDmaBufferWithNotification</code>, any previously allocated DMA buffer must first be freed by calling FreeDmaBufferWithNotification.</p>

<p>During calls to <code>AllocateDmaBufferWithNotification</code> and <b>FreeDmaBufferWithNotification</b>, the DMA engine must be in the reset stream state. The DMA engine is in the reset stream state immediately following the call to <a href="..\hdaudio\nc-hdaudio-pallocate-capture-dma-engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate-render-dma-engine.md">AllocateRenderDmaEngine</a>. To change the DMA engine to the run state, call <a href="..\hdaudio\nc-hdaudio-pset-dma-engine-state.md">SetDmaEngineState</a>.</p>

<p>The FIFO size is the maximum number of bytes that the DMA engine can hold in its internal buffer. Depending on the hardware implementation, a DMA engine's FIFO size can either be static or vary dynamically with changes in the stream format. For more information about the FIFO size, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel High Definition Audio Specification</a>.</p>

<p>In Windows Vista and later versions of Windows, a WaveRT miniport driver calls this routine when it receives the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a> property request. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hdaudio.h (include Hdaudio.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate-capture-dma-engine.md">AllocateCaptureDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate-render-dma-engine.md">AllocateRenderDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\ns-hdaudio--hdaudio-bus-interface-v2.md">HDAUDIO_BUS_INTERFACE_V2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537374">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pset-dma-engine-state.md">SetDmaEngineState</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-psetup-dma-engine-with-bdl.md">SetupDmaEngineWithBdl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PALLOCATE_DMA_BUFFER_WITH_NOTIFICATION callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
