---
UID: NN:dmusicks.IMiniportDMus
title: IMiniportDMus
author: windows-driver-content
description: The IMiniportDMus interface is the primary interface for a DMus miniport driver for a DirectMusic synthesizer device.
old-location: audio\iminiportdmus.htm
old-project: audio
ms.assetid: 12cd3533-1830-46cd-a1eb-350f7461a61d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISynthSinkDMus, ISynthSinkDMus::SyncToMaster, SyncToMaster
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMiniportDMus
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
req.irql: 
req.typenames: DMUS_STREAM_TYPE
---

# IMiniportDMus interface



## -description
The <code>IMiniportDMus</code> interface is the primary interface for a DMus miniport driver for a DirectMusic synthesizer device. The DMus port driver communicates with the miniport driver through this interface. The adapter driver creates the DMus miniport object and passes the object's <code>IMiniportDMus</code> interface pointer to the port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a> method (see the code example in <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a>). <code>IMiniportDMus</code> inherits from the <a href="..\portcls\nn-portcls-iminiport.md">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportDMus</code> object to an <a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a> object. The PortCls system driver registers this pair with the system as a DirectMusic filter (see <a href="https://msdn.microsoft.com/622aa4ae-c855-4088-bc1a-30dff7a24d23">MIDI and DirectMusic Filters</a>).

The <code>IMiniportDMus</code> interface provides methods for initializing the miniport driver, for creating a new DirectMusic stream, and for notifying the miniport driver of an interrupt service request.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportDMus</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IMiniportDMus</b> also has these types of members:

The <b>IMiniportDMus</b> interface has these methods.

The <code>Init</code> method initializes the DMus miniport object.

The <code>NewStream</code> method creates a new instance of a logical stream associated with a specified physical channel.


   This method does not currently need to be implemented in the miniport driver. The<code> Service</code> method is currently unused.

 


## -members
The <b>IMiniportDMus</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536700">IMiniportDMus::Init</a>
</td>
<td align="left" width="63%">
The <code>Init</code> method initializes the DMus miniport object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536701">IMiniportDMus::NewStream</a>
</td>
<td align="left" width="63%">
The <code>NewStream</code> method creates a new instance of a logical stream associated with a specified physical channel.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536702">IMiniportDMus::Service</a>
</td>
<td align="left" width="63%">

   This method does not currently need to be implemented in the miniport driver. The<code> Service</code> method is currently unused.

</td>
</tr>
</table>The <code>Init</code> method initializes the DMus miniport object.

The <code>NewStream</code> method creates a new instance of a logical stream associated with a specified physical channel.


   This method does not currently need to be implemented in the miniport driver. The<code> Service</code> method is currently unused.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dmusicks.h (include Dmusicks.h)</dt>
</dl>
</td>
</tr>
</table>