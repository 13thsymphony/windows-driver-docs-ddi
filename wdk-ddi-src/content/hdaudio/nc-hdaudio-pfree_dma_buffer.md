---
UID: NC.hdaudio.PFREE_DMA_BUFFER
title: PFREE_DMA_BUFFER
author: windows-driver-content
description: The FreeDmaBuffer routine frees a DMA buffer that was previously allocated by a call to AllocateDmaBuffer.The function pointer type for a FreeDmaBuffer routine is defined as:
old-location: audio\freedmabuffer.htm
old-project: audio
ms.assetid: 658e32d2-40e2-4479-8212-df7140fe6b74
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
req.alt-api: FreeDmaBuffer
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
---

# PFREE_DMA_BUFFER callback



## -description
The <code>FreeDmaBuffer</code> routine frees a DMA buffer that was previously allocated by a call to <b>AllocateDmaBuffer</b>.

The function pointer type for a <code>FreeDmaBuffer</code> routine is defined as:



## -prototype

````
PFREE_DMA_BUFFER FreeDmaBuffer;

NTSTATUS FreeDmaBuffer(
  _In_ PVOID  context,
  _In_ HANDLE handle
)
{ ... }
````


## -parameters

### -param context [in]

Specifies the context value from the <b>Context</b> member of the <a href="audio.hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a> or the <a href="audio.hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a> structure.


### -param handle [in]

Handle identifying the DMA engine. This handle value was obtained from a previous call to <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>.


## -returns
<code>FreeDmaBuffer</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.
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
The <code>FreeDmaBuffer</code> routine is used in conjunction with the <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a> routine. These two routines are available only in the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI. This DDI does not include the <a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a>, <a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>, and <a href="..\hdaudio\nc-hdaudio-pfree_contiguous_dma_buffer.md">FreeContiguousDmaBuffer</a> routines, which are never used in conjunction with <b>AllocateDmaBuffer</b> and <code>FreeDmaBuffer</code>. Unlike <b>SetupDmaEngineWithBdl</b>, which configures the DMA engine to use a previously allocated DMA buffer, <b>AllocateDmaBuffer</b> both allocates a DMA buffer and configures the DMA engine to use the buffer.

The routine fails and returns error code STATUS_INVALID_DEVICE_REQUEST in either of the following circumstances:

The client calls <code>FreeDmaBuffer</code> when no buffer is currently allocated for the DMA engine.

The stream is in a state other than reset.


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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a>
</dt>
<dt>
<a href="audio.hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>
</dt>
<dt>
<a href="audio.hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PFREE_DMA_BUFFER callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

