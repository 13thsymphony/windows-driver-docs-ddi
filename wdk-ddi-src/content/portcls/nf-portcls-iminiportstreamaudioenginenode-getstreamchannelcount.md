---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamChannelCount
title: IMiniportStreamAudioEngineNode::GetStreamChannelCount method
author: windows-driver-content
description: Gets a count of the number of channels available for the stream.
old-location: audio\iminiportstreamaudioenginenode_getstreamchannelcount.htm
old-project: audio
ms.assetid: D39376D8-CD1D-4E07-8017-0B552A4D2E59
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetStreamChannelCount method [Audio Devices], GetStreamChannelCount method [Audio Devices], IMiniportStreamAudioEngineNode interface, GetStreamChannelCount,IMiniportStreamAudioEngineNode.GetStreamChannelCount, IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], GetStreamChannelCount method, IMiniportStreamAudioEngineNode::GetStreamChannelCount, audio.iminiportstreamaudioenginenode_getstreamchannelcount, portcls/IMiniportStreamAudioEngineNode::GetStreamChannelCount
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
-	IMiniportStreamAudioEngineNode.GetStreamChannelCount
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IMiniportStreamAudioEngineNode::GetStreamChannelCount method
Gets a count of the number of channels available for the stream.

## Syntax

```
NTSTATUS GetStreamChannelCount(
  eChannelTargetType targetType,
  UINT32             *pulChannelCount
);
```

## Parameters

`targetType`

An <a href="https://msdn.microsoft.com/library/windows/hardware/dn302034">eChannelTargetType</a> enumerated value that specifies the  target node type.

`pulChannelCount`

The number of available channels.


## Return Value

<b>GetStreamChannelCount</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | portcls.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265090">IMiniportStreamAudioEngineNode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn302034">eChannelTargetType</a>