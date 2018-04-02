---
UID: NF:portcls.IMiniportAudioEngineNode.GetBufferSizeRange
title: IMiniportAudioEngineNode::GetBufferSizeRange method
author: windows-driver-content
description: Gets the minimum and maximum buffer size that the hardware audio engine can support.
old-location: audio\iminiportaudioenginenode_getbuffersizerange.htm
old-project: audio
ms.assetid: 75CBDD4F-618F-4618-9D53-4A8DF40992B0
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetBufferSizeRange method [Audio Devices], GetBufferSizeRange method [Audio Devices], IMiniportAudioEngineNode interface, GetBufferSizeRange,IMiniportAudioEngineNode.GetBufferSizeRange, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetBufferSizeRange method, IMiniportAudioEngineNode::GetBufferSizeRange, audio.iminiportaudioenginenode_getbuffersizerange, portcls/IMiniportAudioEngineNode::GetBufferSizeRange
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
-	IMiniportAudioEngineNode.GetBufferSizeRange
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IMiniportAudioEngineNode::GetBufferSizeRange method
Gets the minimum and maximum buffer size that the hardware audio engine can support.

## Syntax

```
NTSTATUS GetBufferSizeRange(
  ULONG                           ulNodeId,
  KSDATAFORMAT_WAVEFORMATEX       *pKsDataFormatWfx,
  KSAUDIOENGINE_BUFFER_SIZE_RANGE *pBufferSizeRange
);
```

## Parameters

`ulNodeId`

The ID for the node that represents the audio device.

`pKsDataFormatWfx`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537095">KSDATAFORMAT_WAVEFORMATEX</a> structure that represents the audio data format for the audio device.

`pBufferSizeRange`

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh450864">KSAUDIOENGINE_BUFFER_SIZE_RANGE</a> structure that represents the minimum and maximum buffer size that the hardware audio engine can support at the time when it is called.


## Return Value

<b>GetBufferSizeRange</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | portcls.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>