---
UID: NF.portcls.IMiniportAudioEngineNode.SetDeviceChannelVolume
title: IMiniportAudioEngineNode::SetDeviceChannelVolume method
author: windows-driver-content
description: Sets the volume level for a given channel of the audio device.
old-location: audio\iminiportaudioenginenode_setdevicechannelvolume.htm
old-project: audio
ms.assetid: 05DA619B-B36A-4E14-9F63-E12E90E0BDCD
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportAudioEngineNode, IMiniportAudioEngineNode::SetDeviceChannelVolume, SetDeviceChannelVolume
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
req.alt-api: IMiniportAudioEngineNode.SetDeviceChannelVolume
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

# IMiniportAudioEngineNode::SetDeviceChannelVolume method



## -description
Sets the volume level for a given channel of the audio device.



## -syntax

````
NTSTATUS SetDeviceChannelVolume(
  [in] ULONG  ulNodeId,
  [in] UINT32 ulChannel,
  [in] LONG   lVolume
);
````


## -parameters

### -param ulNodeId [in]

The ID for the node that represents the audio device.


### -param ulChannel [in]

The audio device channel.


### -param lVolume [in]

The volume level to which the channel will be set.


## -returns
<b>SetDeviceChannelVolume</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.


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
<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::SetDeviceChannelVolume method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

