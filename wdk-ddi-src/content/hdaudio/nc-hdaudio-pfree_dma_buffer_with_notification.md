---
UID: NC.hdaudio.PFREE_DMA_BUFFER_WITH_NOTIFICATION
title: PFREE_DMA_BUFFER_WITH_NOTIFICATION
author: windows-driver-content
description: The FreeDmaBufferWithNotification routine frees a DMA buffer that was previously allocated by a call to AllocateDmaBufferWithNotification.The function pointer type for a FreeDmaBufferWithNotification routine is defined as follows.
old-location: audio\freedmabufferwithnotification.htm
old-project: audio
ms.assetid: 98fc6201-d9b4-4c85-b624-011f360df068
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SM_SetRNIDMgmtInfo_OUT, PSM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
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
req.alt-api: FreeDmaBufferWithNotification
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
req.irql: PASSIVE_LEVEL
---

# PFREE_DMA_BUFFER_WITH_NOTIFICATION callback



## -description
The <code>FreeDmaBufferWithNotification</code> routine frees a DMA buffer that was previously allocated by a call to <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer_with_notification.md">AllocateDmaBufferWithNotification</a>.

The function pointer type for a FreeDmaBufferWithNotification routine is defined as follows.



## -prototype

````
PFREE_DMA_BUFFER_WITH_NOTIFICATION FreeDmaBufferWithNotification;

NTSTATUS FreeDmaBufferWithNotification(
  _In_ PVOID  context,
  _In_ HANDLE handle,
  _In_ PMDL   bufferMdl,
  _In_ SIZE_T bufferSize
)
{ ... }
````


## -parameters

### -param context [in]

Specifies the context value from the Context member of the <a href="audio.hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a> structure.


### -param handle [in]

Handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a> or <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>.


### -param bufferMdl [in]

A pointer to the buffer MDL. This value was obtained from a previous call to AllocateDmaBufferWithNotification.


### -param bufferSize [in]

The size of the buffer to be freed. This value was obtained from a previous call to AllocateDmaBufferWithNotification.


## -returns
<code>FreeDmaBufferWithNotification</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, <code>FreeDmaBufferWithNotification</code> returns an appropriate error code. The following table shows some of the possible return error codes.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>Indicates that the caller is running at an IRQL that is too high.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>Indicates that the <i>handle</i> parameter value is invalid.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>Indicates that the stream is not in the reset state or that no buffer is currently allocated for the DMA engine.

 


## -remarks
The <code>FreeDmaBufferWithNotification</code> routine is used together with the AllocateDmaBufferWithNotification routine. These two routines are available only in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI.

Callers of FreeDmaBufferWithNotification must be running at IRQL PASSIVE_LEVEL.


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
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of Windows.

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
<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer_with_notification.md">AllocateDmaBufferWithNotification</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>
</dt>
<dt>
<a href="audio.hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PFREE_DMA_BUFFER_WITH_NOTIFICATION callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

