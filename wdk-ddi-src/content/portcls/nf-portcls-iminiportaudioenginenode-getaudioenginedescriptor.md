---
UID: NF:portcls.IMiniportAudioEngineNode.GetAudioEngineDescriptor
title: IMiniportAudioEngineNode::GetAudioEngineDescriptor method
author: windows-driver-content
description: Gets the descriptor for the audio engine node.
old-location: audio\iminiportaudioenginenode_getaudioenginedescriptor.htm
old-project: audio
ms.assetid: B8D09AB4-1F36-44E1-8D4F-33E7E4DBBFE3
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetAudioEngineDescriptor method [Audio Devices], GetAudioEngineDescriptor method [Audio Devices], IMiniportAudioEngineNode interface, GetAudioEngineDescriptor,IMiniportAudioEngineNode.GetAudioEngineDescriptor, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetAudioEngineDescriptor method, IMiniportAudioEngineNode::GetAudioEngineDescriptor, audio.iminiportaudioenginenode_getaudioenginedescriptor, portcls/IMiniportAudioEngineNode::GetAudioEngineDescriptor
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
-	IMiniportAudioEngineNode.GetAudioEngineDescriptor
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IMiniportAudioEngineNode::GetAudioEngineDescriptor method
Gets the descriptor for the audio engine node.

## Syntax

```
NTSTATUS GetAudioEngineDescriptor(
  ULONG                    ulNodeId,
  KSAUDIOENGINE_DESCRIPTOR *pAudioEngineDescriptor
);
```

## Parameters

`ulNodeId`

The ID of the audio engine node.

`pAudioEngineDescriptor`

Audio engine descriptor object. This parameter is of type <a href="https://msdn.microsoft.com/library/windows/hardware/hh450862">KSAUDIOENGINE_DESCRIPTOR</a>.


## Return Value

<b>GetAudioEngineDescriptor</b> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | portcls.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450862">KSAUDIOENGINE_DESCRIPTOR</a>