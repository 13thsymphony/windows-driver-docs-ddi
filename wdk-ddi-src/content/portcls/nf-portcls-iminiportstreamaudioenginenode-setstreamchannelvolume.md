---
UID: NF:portcls.IMiniportStreamAudioEngineNode.SetStreamChannelVolume
title: IMiniportStreamAudioEngineNode::SetStreamChannelVolume method
author: windows-driver-content
description: Sets the volume level to be applied to the audio stream.
old-location: audio\iminiportstreamaudioenginenode_setstreamchannelvolume.htm
old-project: audio
ms.assetid: 0110979E-8C57-4394-B43E-BCC7B178A0AF
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], SetStreamChannelVolume method, IMiniportStreamAudioEngineNode::SetStreamChannelVolume, SetStreamChannelVolume method [Audio Devices], SetStreamChannelVolume method [Audio Devices], IMiniportStreamAudioEngineNode interface, SetStreamChannelVolume,IMiniportStreamAudioEngineNode.SetStreamChannelVolume, audio.iminiportstreamaudioenginenode_setstreamchannelvolume, portcls/IMiniportStreamAudioEngineNode::SetStreamChannelVolume
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
-	IMiniportStreamAudioEngineNode.SetStreamChannelVolume
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IMiniportStreamAudioEngineNode::SetStreamChannelVolume method
Sets the volume level to be applied to the audio stream.

## Syntax

```
NTSTATUS SetStreamChannelVolume(
  UINT32           Channel,
  LONG             TargetVolume,
  AUDIO_CURVE_TYPE CurveType,
  ULONGLONG        CurveDuration
);
```

## Parameters

`Channel`

The audio stream channel.

`TargetVolume`

The volume level to be applied to the audio stream.

`CurveType`

The curve algorithm that will be used  to set the volume level. The curve types are represented by the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh831852">AUDIO_CURVE_TYPE</a> enum.

`CurveDuration`

The length of time over which the curve algorithm will be applied.


## Return Value

<b>SetStreamChannelVolume</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | portcls.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265090">IMiniportStreamAudioEngineNode</a>