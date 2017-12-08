---
UID: NN.portcls.IMiniportStreamAudioEngineNode2
title: IMiniportStreamAudioEngineNode2
author: windows-driver-content
description: The IMiniportStreamAudioEngineNode2 interface allows an audio miniport driver to extend the capabilities of the IMiniportStreamAudioEngineNode interface.
old-location: audio\iminiportstreamaudioenginenode2.htm
old-project: audio
ms.assetid: 38888C17-31FC-47F4-A49B-A46A9DF962AF
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PcUnregisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMiniportStreamAudioEngineNode2
req.alt-loc: Portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# IMiniportStreamAudioEngineNode2 interface



## -description
The <b>IMiniportStreamAudioEngineNode2</b> interface allows an audio miniport driver to extend the capabilities of the <a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a> interface.


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportStreamAudioEngineNode2</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IMiniportStreamAudioEngineNode2</b> also has these types of members:

The <b>IMiniportStreamAudioEngineNode2</b> interface has these methods.

Sets the current cursor position in the last audio data stream that was written to the audio buffer.

 

## -members
The <b>IMiniportStreamAudioEngineNode2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="audio.iminiportstreamaudioenginenode2_setstreamcurrentwritepositionforlastbuffer">SetStreamCurrentWritePositionForLastBuffer</a>
</td>
<td align="left" width="63%">
Sets the current cursor position in the last audio data stream that was written to the audio buffer.
</td>
</tr>
</table>Sets the current cursor position in the last audio data stream that was written to the audio buffer.

 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8.1
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012 R2
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