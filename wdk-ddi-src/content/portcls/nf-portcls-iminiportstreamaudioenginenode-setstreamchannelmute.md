---
UID: NF.portcls.IMiniportStreamAudioEngineNode.SetStreamChannelMute
title: IMiniportStreamAudioEngineNode::SetStreamChannelMute method
author: windows-driver-content
description: Sets the state of the Mute node in the path of the audio stream.
old-location: audio\iminiportstreamaudioenginenode_setstreamchannelmute.htm
old-project: audio
ms.assetid: AAD0101E-13FB-48A2-8834-799472B93931
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode::SetStreamChannelMute, SetStreamChannelMute
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
req.alt-api: IMiniportStreamAudioEngineNode.SetStreamChannelMute
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

# IMiniportStreamAudioEngineNode::SetStreamChannelMute method



## -description
Sets the state of the Mute node in the path of the audio stream.



## -syntax

````
NTSTATUS SetStreamChannelMute(
  [in] UINT32 ulChannel,
  [in] BOOL   bMute
);
````


## -parameters

### -param ulChannel [in]

The channel for the audio stream.


### -param bMute [in]

The state to which the Mute node will be set.


## -returns
<b>SetStreamChannelMute</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

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
<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportStreamAudioEngineNode::SetStreamChannelMute method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

