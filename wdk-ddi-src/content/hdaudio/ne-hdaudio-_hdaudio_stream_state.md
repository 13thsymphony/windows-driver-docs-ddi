---
UID: NE.hdaudio._HDAUDIO_STREAM_STATE
title: _HDAUDIO_STREAM_STATE
author: windows-driver-content
description: The HDAUDIO_STREAM_STATE enumeration defines constants that specify the different stream states supported by HDAudio.
old-location: audio\hdaudio_stream_state.htm
old-project: audio
ms.assetid: A1029A2D-980F-44F5-B7D6-1C37F97D0368
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _HDAUDIO_STREAM_STATE, HDAUDIO_STREAM_STATE, *PHDAUDIO_STREAM_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: hdaudio.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HDAUDIO_STREAM_STATE
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
---

# _HDAUDIO_STREAM_STATE enumeration



## -description
The <b>HDAUDIO_STREAM_STATE</b> enumeration defines constants that specify the different stream states supported by HDAudio.


## -syntax

````
typedef enum _HDAUDIO_STREAM_STATE { 
  ResetState  = 0,
  StopState   = 1,
  PauseState  = 1,
  RunState    = 2
} HDAUDIO_STREAM_STATE, *PHDAUDIO_STREAM_STATE;
````


## -enum-fields

### -field ResetState

The reset state.

### -field StopState

The stop state.

### -field PauseState

The pause state.

### -field RunState

The run state.

## -remarks
This enumeration is used by the <a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">PSET_DMA_ENGINE_STATE</a>.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Hdaudio.h</dt>
</dl>
</td>
</tr>
</table>