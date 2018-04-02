---
UID: NF:portcls.IMiniportMidiStream.SetState
title: IMiniportMidiStream::SetState method
author: windows-driver-content
description: The SetState method sets the stream's transport state to a new state value.
old-location: audio\iminiportmidistream_setstate.htm
old-project: audio
ms.assetid: ee78013c-7660-4017-97ec-eff9068b707a
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IMiniportMidiStream, IMiniportMidiStream interface [Audio Devices], SetState method, IMiniportMidiStream::SetState, SetState method [Audio Devices], SetState method [Audio Devices], IMiniportMidiStream interface, SetState,IMiniportMidiStream.SetState, audio.iminiportmidistream_setstate, audmp-routines_23f064df-faef-4c45-a58e-c5e3e1d7d7a5.xml, portcls/IMiniportMidiStream::SetState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportMidiStream.SetState
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IMiniportMidiStream::SetState method
The <code>SetState</code> method sets the stream's transport state to a new state value.

## Syntax

```
NTSTATUS SetState(
  KSSTATE State
);
```

## Parameters

`State`

Specifies the new state that the stream is to be set to. This parameter is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a> enumeration value. For more information, see the following Remarks section.


## Return Value

<code>SetState</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## Remarks

For an audio filter graph, the four <a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a> enumeration values are interpreted as follows:

<ul>
<li>
KSSTATE_RUN 

Data transport in the current audio filter graph is running and functioning as normal.

</li>
<li>
KSSTATE_ACQUIRE 

This is a transitional state that helps to manage the transition between KSSTATE_RUN and KSSTATE_STOP.

</li>
<li>
KSSTATE_PAUSE 

This is a transitional state that helps to manage the transition between KSSTATE_RUN and KSSTATE_STOP. 

</li>
<li>
KSSTATE_STOP 

Data transport is stopped in the current audio filter graph.

</li>
</ul>
For most miniport drivers, KSSTATE_ACQUIRE and KSSTATE_PAUSE are indistinguishable. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff536710">IMiniportMidi::NewStream</a> method sets the initial state of the stream to KSSTATE_STOP.

Transitions always occur in one of the following two sequences:

<ul>
<li>
STOP -&gt; ACQUIRE -&gt; PAUSE -&gt; RUN

</li>
<li>
RUN -&gt; PAUSE -&gt; ACQUIRE -&gt; STOP

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536710">IMiniportMidi::NewStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536704">IMiniportMidiStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565110">KSPROPERTY_CONNECTION_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a>