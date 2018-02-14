---
UID: NF:portcls.IMiniportAudioEngineNode.SetGfxState
title: IMiniportAudioEngineNode::SetGfxState method
author: windows-driver-content
description: Sets the state of the global effects (GFX) node in the audio engine.
old-location: audio\iminiportaudioenginenode_setgfxstate.htm
old-project: audio
ms.assetid: B073D354-14FB-477E-BBD7-8BD282696EF4
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: SetGfxState, IMiniportAudioEngineNode, SetGfxState method [Audio Devices], IMiniportAudioEngineNode::SetGfxState, IMiniportAudioEngineNode interface [Audio Devices], SetGfxState method, SetGfxState method [Audio Devices], IMiniportAudioEngineNode interface, portcls/IMiniportAudioEngineNode::SetGfxState, audio.iminiportaudioenginenode_setgfxstate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
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
req.lib: portcls.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IMiniportAudioEngineNode.SetGfxState
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---


# SetGfxState method
Sets the state of the global effects (GFX) node in the audio engine.

## Syntax

````
NTSTATUS SetGfxState(
  [in] ULONG ulNodeId,
  [in] BOOL  bEnable
);
````

## Parameters

`ulNodeId`

The ID of the GFX node.

`bEnable`

The state of the GFX node.


## Return Value

<b>SetGfxState</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h |
| **Library** | portcls.h |

## See Also

<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::SetGfxState method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>