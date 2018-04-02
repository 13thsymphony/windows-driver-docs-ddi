---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetStreamChannelMute
title: IMiniportStreamAudioEngineNode::SetStreamChannelMute method
author: windows-driver-content
description: Sets the state of the Mute node in the path of the audio stream.
old-location: audio\iminiportstreamaudioenginenode_setstreamchannelmute.htm
old-project: audio
ms.assetid: AAD0101E-13FB-48A2-8834-799472B93931
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], SetStreamChannelMute method, IMiniportStreamAudioEngineNode::SetStreamChannelMute, SetStreamChannelMute method [Audio Devices], SetStreamChannelMute method [Audio Devices], IMiniportStreamAudioEngineNode interface, SetStreamChannelMute,IMiniportStreamAudioEngineNode.SetStreamChannelMute, audio.iminiportstreamaudioenginenode_setstreamchannelmute, portcls/IMiniportStreamAudioEngineNode::SetStreamChannelMute
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
-	IMiniportStreamAudioEngineNode.SetStreamChannelMute
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IMiniportStreamAudioEngineNode::SetStreamChannelMute method
Sets the state of the Mute node in the path of the audio stream.

## Syntax

```
NTSTATUS SetStreamChannelMute(
  UINT32 ulChannel,
  BOOL   bMute
);
```

## Parameters

`ulChannel`

The channel for the audio stream.

`bMute`

The state to which the Mute node will be set.


## Return Value

<b>SetStreamChannelMute</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | portcls.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265090">IMiniportStreamAudioEngineNode</a>