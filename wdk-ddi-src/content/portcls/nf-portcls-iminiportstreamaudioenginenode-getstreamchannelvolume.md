---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamChannelVolume
title: IMiniportStreamAudioEngineNode::GetStreamChannelVolume method
author: windows-driver-content
description: Gets the current volume level that is applied to the audio stream.
old-location: audio\iminiportstreamaudioenginenode_getstreamchannelvolume.htm
old-project: audio
ms.assetid: 0BD6FCB7-1705-4343-AD41-7362FE095ECB
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetStreamChannelVolume method [Audio Devices], GetStreamChannelVolume method [Audio Devices], IMiniportStreamAudioEngineNode interface, GetStreamChannelVolume,IMiniportStreamAudioEngineNode.GetStreamChannelVolume, IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], GetStreamChannelVolume method, IMiniportStreamAudioEngineNode::GetStreamChannelVolume, audio.iminiportstreamaudioenginenode_getstreamchannelvolume, portcls/IMiniportStreamAudioEngineNode::GetStreamChannelVolume
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
-	IMiniportStreamAudioEngineNode.GetStreamChannelVolume
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# GetStreamChannelVolume method
Gets the current volume level that is applied to the audio stream.

## Syntax

````
NTSTATUS GetStreamChannelVolume(
  [in]  UINT32  ulChannel,
  [out] LONG   *plValue
);
````

## Parameters

`ulChannel`

The audio stream channel.

`plValue`

The current volume level.


## Return Value

<b>GetStreamChannelVolume</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | portcls.h |

## See Also

<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>