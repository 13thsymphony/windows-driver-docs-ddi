---
UID: NN:portcls.IPortWaveCyclic
title: IPortWaveCyclic
author: windows-driver-content
description: The IPortWaveCyclic interface is the WaveCyclic port driver's primary interface.
old-location: audio\iportwavecyclic.htm
old-project: audio
ms.assetid: de241c4c-2012-4d57-b069-d169b1e0aec3
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.iportwavecyclic, IPortWaveCyclic interface [Audio Devices], IPortWaveCyclic interface [Audio Devices], described, IPortWaveCyclic, portcls/IPortWaveCyclic, audmp-routines_079bd398-d9f2-4a35-9ee0-6ced8fecdeb4.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IPortWaveCyclic
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IPortWaveCyclic interface

The <code>IPortWaveCyclic</code> interface is the WaveCyclic port driver's primary interface. The PortCls system driver implements this interface and exposes it to the adapter driver that implements the <a href="..\portcls\nn-portcls-iminiportwavecyclic.md">IMiniportWaveCyclic</a> object. The <code>IPortWaveCyclic</code> interface provides a notification method that the miniport driver's interrupt service routine calls. Subordinate and bus-master DMA channels can also be instantiated on this interface. An adapter driver creates an <code>IPortWaveCyclic</code> object by calling <a href="..\portcls\nf-portcls-pcnewport.md">PcNewPort</a> and specifying REFIID <b>IID_IPortWaveCyclic</b>. <code>IPortWaveCyclic</code> inherits from the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <b>IMiniportWaveCyclic</b> object to an <code>IPortWaveCyclic</code> object. The PortCls system driver registers this pair with the system as a <a href="https://msdn.microsoft.com/9e364c8f-55c3-4ec9-a9ce-9ee0f6a0746b">wave filter</a>.

## Methods

<p>The <b>IPortWaveCyclic</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [portcls.IPortWaveCyclic.NewMasterDmaChannel](nf-portcls-iportwavecyclic-newmasterdmachannel.md) | The NewMasterDmaChannel method creates a new instance of a bus-master DMA channel. |
| [portcls.IPortWaveCyclic.NewSlaveDmaChannel](nf-portcls-iportwavecyclic-newslavedmachannel.md) | The NewSlaveDmaChannel method creates a new instance of a subordinate DMA channel. |
| [portcls.IPortWaveCyclic.Notify](nf-portcls-iportwavecyclic-notify.md) | The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR). |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | portcls.h |