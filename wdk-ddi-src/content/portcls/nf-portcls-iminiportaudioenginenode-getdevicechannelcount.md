---
UID: NF.portcls.IMiniportAudioEngineNode.GetDeviceChannelCount
title: IMiniportAudioEngineNode::GetDeviceChannelCount method
author: windows-driver-content
description: Gets a count of the number of channels supported by the audio device.
old-location: audio\iminiportaudioenginenode_getdevicechannelcount.htm
old-project: audio
ms.assetid: 978193AE-55CD-4255-8722-A1E008E98F08
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportAudioEngineNode, IMiniportAudioEngineNode::GetDeviceChannelCount, GetDeviceChannelCount
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
req.alt-api: IMiniportAudioEngineNode.GetDeviceChannelCount
req.alt-loc: Portcls.h
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
---

# IMiniportAudioEngineNode::GetDeviceChannelCount method



## -description
Gets a count of the number of channels supported by the audio device.



## -syntax

````
NTSTATUS GetDeviceChannelCount(
  [in]  ULONG              ulNodeId,
  [in]  eChannelTargetType targetType,
  [out] UINT32             *pulChannelCount
);
````


## -parameters

### -param ulNodeId [in]

The ID of the node that represents the audio device.


### -param targetType [in]

An <a href="..\portcls\ne-portcls-echanneltargettype.md">eChannelTargetType</a> enumerated value that specifies the types of target nodes in the channels. For example, there could be Volume, Mute or PeakMeter nodes.


### -param pulChannelCount [out]

The number of channels supported by the audio device.


## -returns
<b>GetDeviceChannelCount</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\ne-portcls-echanneltargettype.md">eChannelTargetType</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::GetDeviceChannelCount method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

