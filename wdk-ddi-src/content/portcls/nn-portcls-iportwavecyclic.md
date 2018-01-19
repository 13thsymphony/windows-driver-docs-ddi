---
UID : NN:portcls.IPortWaveCyclic
title : IPortWaveCyclic
author : windows-driver-content
description : The IPortWaveCyclic interface is the WaveCyclic port driver's primary interface.
old-location : audio\iportwavecyclic.htm
old-project : audio
ms.assetid : de241c4c-2012-4d57-b069-d169b1e0aec3
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PcUnregisterIoTimeout
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : portcls.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IPortWaveCyclic
req.alt-loc : portcls.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Portcls.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
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
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum UMDF version** |  |
| **Header** | portcls.h |
| **DLL** |  |