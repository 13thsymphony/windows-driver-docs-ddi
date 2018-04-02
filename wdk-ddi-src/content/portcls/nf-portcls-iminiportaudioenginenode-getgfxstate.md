---
UID: NF:portcls.IMiniportAudioEngineNode.GetGfxState
title: IMiniportAudioEngineNode::GetGfxState method
author: windows-driver-content
description: Gets the state of the global effects (GFX) node in the audio engine.
old-location: audio\iminiportaudioenginenode_getgfxstate.htm
old-project: audio
ms.assetid: C2D4EB3E-0A39-4458-B0E7-C6D943AB4203
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetGfxState method [Audio Devices], GetGfxState method [Audio Devices], IMiniportAudioEngineNode interface, GetGfxState,IMiniportAudioEngineNode.GetGfxState, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetGfxState method, IMiniportAudioEngineNode::GetGfxState, audio.iminiportaudioenginenode_getgfxstate, portcls/IMiniportAudioEngineNode::GetGfxState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IMiniportAudioEngineNode.GetGfxState
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IMiniportAudioEngineNode::GetGfxState method
Gets the state of the global effects (GFX) node in the audio engine.

## Syntax

```
NTSTATUS GetGfxState(
  ULONG ulNodeId,
  BOOL  *pbEnable
);
```

## Parameters

`ulNodeId`

The ID of the GFX node.

`pbEnable`

Pointer to a <b>BOOL</b> data type.


## Return Value

<b>GetGfxState</b> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | portcls.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>