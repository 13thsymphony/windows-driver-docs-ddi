---
UID: NF:portcls.IMiniportAudioEngineNode.SetDeviceChannelMute
title: IMiniportAudioEngineNode::SetDeviceChannelMute method
author: windows-driver-content
description: Sets the state of the Mute node for the audio device channel.
old-location: audio\iminiportaudioenginenode_setdevicechannelmute.htm
old-project: audio
ms.assetid: 272B83D4-AACE-419D-9DD7-A1AE1C8A931A
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], SetDeviceChannelMute method, IMiniportAudioEngineNode::SetDeviceChannelMute, SetDeviceChannelMute method [Audio Devices], SetDeviceChannelMute method [Audio Devices], IMiniportAudioEngineNode interface, SetDeviceChannelMute,IMiniportAudioEngineNode.SetDeviceChannelMute, audio.iminiportaudioenginenode_setdevicechannelmute, portcls/IMiniportAudioEngineNode::SetDeviceChannelMute
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
req.lib: portcls.h
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
-	IMiniportAudioEngineNode.SetDeviceChannelMute
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# SetDeviceChannelMute method
Sets the state of the Mute node for the audio device channel.

## Syntax

````
NTSTATUS SetDeviceChannelMute(
  [in] ULONG  ulNodeId,
  [in] UINT32 ulChannel,
  [in] BOOL   bMute
);
````

## Parameters

`ulNodeId`

The ID for the node that represents the audio device.

`ulChannel`

The audio device channel.

`bMute`

The state to which the Mute node for the audio device channel will be set.


## Return Value

<b>SetDeviceChannelMute</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | portcls.h |
| **Library** | portcls.h |

## See Also

<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::SetDeviceChannelMute method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>