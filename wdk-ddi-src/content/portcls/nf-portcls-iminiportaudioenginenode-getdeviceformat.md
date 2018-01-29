---
UID : NF:portcls.IMiniportAudioEngineNode.GetDeviceFormat
title : IMiniportAudioEngineNode::GetDeviceFormat method
author : windows-driver-content
description : Gets the audio data format for an audio device.
old-location : audio\iminiportaudioenginenode_getdeviceformat.htm
old-project : audio
ms.assetid : 6EA01AE7-E5D5-4182-862D-2901185C2BF8
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : GetDeviceFormat, portcls/IMiniportAudioEngineNode::GetDeviceFormat, IMiniportAudioEngineNode interface [Audio Devices], GetDeviceFormat method, IMiniportAudioEngineNode, GetDeviceFormat method [Audio Devices], audio.iminiportaudioenginenode_getdeviceformat, IMiniportAudioEngineNode::GetDeviceFormat, GetDeviceFormat method [Audio Devices], IMiniportAudioEngineNode interface
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : portcls.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# GetDeviceFormat method
Gets the audio data format for an audio device.

## Syntax

````
NTSTATUS GetDeviceFormat(
  [in]  ULONG                     ulNodeId,
  [out] KSDATAFORMAT_WAVEFORMATEX *pFormat,
  [in]  ULONG                     ulBufferSize
);
````

## Parameters

`ulNodeId`

The ID of the device node.

`pFormat`

A structure of type  <a href="..\ksmedia\ns-ksmedia-ksdataformat_waveformatex.md">KSDATAFORMAT_WAVEFORMATEX</a> that represents the audio data format for the device.

`ulBufferSize`

The audio data buffer size.


## Return Value

<b>GetDeviceFormat</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>

<a href="..\ksmedia\ns-ksmedia-ksdataformat_waveformatex.md">KSDATAFORMAT_WAVEFORMATEX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::GetDeviceFormat method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>