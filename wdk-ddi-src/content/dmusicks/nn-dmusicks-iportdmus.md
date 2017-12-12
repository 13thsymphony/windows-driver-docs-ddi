---
UID: NN.dmusicks.IPortDMus
title: IPortDMus
author: windows-driver-content
description: The IPortDMus interface is the DMus port driver's primary interface.
old-location: audio\iportdmus.htm
old-project: audio
ms.assetid: 96388400-56f9-4a43-bc37-cfe6cfb233cb
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: DMUS_STREAM_TYPE, DMUS_STREAM_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dmusicks.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortDMus
req.alt-loc: dmusicks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# IPortDMus interface



## -description
The <code>IPortDMus</code> interface is the DMus port driver's primary interface. The PortCls system driver implements this interface and exposes it to the adapter driver that implements the <a href="..\dmusicks\nn-dmusicks-iminiportdmus.md">IMiniportDMus</a> object. An adapter driver creates an <b>IPortWaveDMus</b> object by calling <a href="audio.pcnewport">PcNewPort</a> with REFIID <b>IID_IPortWaveDMus</b> (see the code example in <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a>). <code>IPortDMus</code> inherits from the <a href="..\portcls\nn-portcls-iportmidi.md">IPortMidi</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <b>IMiniportDMus</b> object to an <code>IPortDMus</code> object. The PortCls system driver registers this pair with the system as a DirectMusic filter (see <a href="https://msdn.microsoft.com/622aa4ae-c855-4088-bc1a-30dff7a24d23">MIDI and DirectMusic Filters</a>).



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortDMus</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dmusicks.h</dt>
</dl>
</td>
</tr>
</table>