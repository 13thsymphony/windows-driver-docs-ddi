---
UID: NF:portcls.IMiniportAudioEngineNode.GetSupportedDeviceFormats
title: IMiniportAudioEngineNode::GetSupportedDeviceFormats method
author: windows-driver-content
description: Gets the supported audio data formats for the audio device.
old-location: audio\iminiportaudioenginenode_getsupporteddeviceformats.htm
old-project: audio
ms.assetid: 2B27E92C-8781-4499-A1E0-7C1BBFFAA2DF
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetSupportedDeviceFormats method [Audio Devices], GetSupportedDeviceFormats method [Audio Devices], IMiniportAudioEngineNode interface, GetSupportedDeviceFormats,IMiniportAudioEngineNode.GetSupportedDeviceFormats, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetSupportedDeviceFormats method, IMiniportAudioEngineNode::GetSupportedDeviceFormats, audio.iminiportaudioenginenode_getsupporteddeviceformats, portcls/IMiniportAudioEngineNode::GetSupportedDeviceFormats
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
-	IMiniportAudioEngineNode.GetSupportedDeviceFormats
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# GetSupportedDeviceFormats method
Gets the supported audio data formats for the audio device.

## Syntax

````
NTSTATUS GetSupportedDeviceFormats(
  [in]  ULONG           ulNodeId,
  [out] KSMULTIPLE_ITEM *pFormats,
  [in]  ULONG           ulBufferSize
);
````

## Parameters

`ulNodeId`

The ID of the node that represents the audio device.

`pFormats`

A structure of type <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff563441(v=vs.85).aspx">KSMULTIPLE_ITEM</a> that points to the array of audio data formats supported by the audio device.

`ulBufferSize`

The buffer size for the audio data format information.


## Return Value

<b>GetSupportedDeviceFormats</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | portcls.h |

## See Also

<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff563441(v=vs.85).aspx">KSMULTIPLE_ITEM</a>



<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>