---
UID: NN:portcls.IPort
title: IPort
author: windows-driver-content
description: The IPort interface is the generic interface for audio port drivers. All audio port drivers expose IPort as part of their lower edge. The adapter driver calls the initialization method on this interface. IPort inherits from the IUnknown interface.
old-location: audio\iport.htm
old-project: audio
ms.assetid: 8aaadfd6-3aca-451b-a5e9-081b083ae51d
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IPort, IPort interface [Audio Devices], IPort interface [Audio Devices], described, audio.iport, audmp-routines_45897b1f-29f6-411d-9963-60f31e1655e7.xml, portcls/IPort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPort
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPort interface

The <code>IPort</code> interface is the generic interface for audio port drivers. All audio port drivers expose <code>IPort</code> as part of their lower edge. The adapter driver calls the initialization method on this interface. <code>IPort</code> inherits from the <b>IUnknown</b> interface.

The <code>IPort</code> interface provides a uniform means for initializing audio port drivers of all types. <code>IPort</code> is the base interface for the following port driver interfaces:
<dl>
<dd>

<a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iportmidi.md">IPortMidi</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iporttopology.md">IPortTopology</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iportwavepci.md">IPortWavePci</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iportwavert.md">IPortWaveRT</a>


</dd>
</dl>Call <a href="..\portcls\nf-portcls-pcnewport.md">PcNewPort</a> to create a port object with one of these interfaces.

## Methods

<p>The <b>IPort</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | portcls.h |