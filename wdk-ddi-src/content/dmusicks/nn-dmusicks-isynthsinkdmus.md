---
UID: NN.dmusicks.ISynthSinkDMus
title: ISynthSinkDMus
author: windows-driver-content
description: The ISynthSinkDMus interface handles wave output for a DirectMusic synthesizer device.
old-location: audio\isynthsinkdmus.htm
old-project: audio
ms.assetid: 3bff4242-3e7b-424e-ac86-121267a2c32a
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
req.alt-api: ISynthSinkDMus
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

# ISynthSinkDMus interface



## -description
The <code>ISynthSinkDMus</code> interface handles wave output for a DirectMusic synthesizer device. The DMus miniport driver provides this interface for use by the wave sink, which calls the methods in the interface to render wave output and to synchronize its sample clock to the master clock. As explained in <a href="https://msdn.microsoft.com/dbd6b95e-f8c8-49f1-ad90-b34821772391">Synthesizer Miniport Driver Overview</a>, the wave sink is implemented in the DMus port driver. To determine whether a DMus miniport driver supports the <code>ISynthSinkDMus</code> interface, the DMus port driver calls the miniport driver stream object's <b>IMXF::QueryInterface</b> method with REFIID <b>IID_ISynthSinkDMus</b>. <code>ISynthSinkDMus</code> inherits from the <a href="..\dmusicks\nn-dmusicks-imxf~r1.md">IMXF</a> interface.

The <code>ISynthSinkDMus</code> interface provides methods to render, convert sample to reference time, convert reference to sample time, and synchronize to the master clock. For information about the use of the <code>ISynthSinkDMus</code> interface, see <a href="https://msdn.microsoft.com/37ba9ad5-8b35-4252-a6fd-46dead924294">A Wave Sink for Kernel-Mode Software Synthesizers</a>.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">ISynthSinkDMus</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.


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