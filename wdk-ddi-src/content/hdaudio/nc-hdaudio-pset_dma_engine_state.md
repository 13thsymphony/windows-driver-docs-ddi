---
UID : NC:hdaudio.PSET_DMA_ENGINE_STATE
title : PSET_DMA_ENGINE_STATE
author : windows-driver-content
description : The SetDmaEngineState routine sets the state of one or more DMA engines to the Running, Stopped, Paused, or Reset state.The function pointer type for a SetDmaEngineState routine is defined as:
old-location : audio\setdmaenginestate.htm
old-project : audio
ms.assetid : 05cfb827-e143-4d77-b378-e02dd381e429
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _SM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
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
req.alt-api : SetDmaEngineState
req.alt-loc : hdaudio.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---


# PSET_DMA_ENGINE_STATE callback function
The <i>SetDmaEngineState</i> routine sets the state of one or more DMA engines to the Running, Stopped, Paused, or Reset state.

The function pointer type for a <i>SetDmaEngineState</i> routine is defined as:

## Syntax

```
PSET_DMA_ENGINE_STATE PsetDmaEngineState;

NTSTATUS PsetDmaEngineState(
  PVOID _context,
  HDAUDIO_STREAM_STATE StreamState,
  ULONG NumberOfHandles,
  PHANDLE Handles
)
{...}
```

## Parameters

`_context`



`StreamState`



`NumberOfHandles`



`Handles`




## Return Value

<i>SetDmaEngineState</i> returns STATUS_SUCCESS if the call succeeds in changing the DMA engines' states. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>Indicates that one of the handles is invalid.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Indicates that one of the parameter values is incorrect (invalid parameter value or bad pointer).
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>Indicates that no buffer is currently allocated for one of the DMA engines.

## Remarks

This routine changes the state of one or more DMA engines to the state that the <i>streamState</i> parameter specifies. The routine synchronizes the state transitions of all the DMA engines that the handles in the <i>handles</i> array identify. For more information, see <a href="https://msdn.microsoft.com/c25f4ca2-8a9f-43bc-a1bf-b71826b446ff">Synchronizing Two or More Streams</a>.

Before calling this routine, set up each DMA engine in the <i>handles</i> array:

If using the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI, call <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a> to set up the DMA engine.

If using the HDAUDIO_BUS_INTERFACE_BDL version of the DDI, call <a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a> to set up the DMA engine.

If no DMA buffer is currently allocated for any DMA engine in the <i>handles</i> array, an attempt to change the stream to any state other than Reset causes the <i>SetDmaEngineState</i> call to fail and return error code STATUS_INVALID_DEVICE_REQUEST.

The stream state cannot transition directly between Running and Reset. Instead, the stream must first pass through an intermediate state of Paused or Stopped:

From a Running or Reset state, the stream state can change directly to either Paused or Stopped.

From a paused or stopped state, the stream state can change directly to either Running or Reset.

A WDM audio driver calls this routine during a call to its <b>SetState</b> method. For example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536720">IMiniportWaveCyclicStream::SetState</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hdaudio.h (include Hdaudio.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>
</dt>
<dt>
<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>
</dt>
<dt>
<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536720">IMiniportWaveCyclicStream::SetState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PSET_DMA_ENGINE_STATE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>