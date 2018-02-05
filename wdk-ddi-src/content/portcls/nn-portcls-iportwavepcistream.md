---
UID : NN:portcls.IPortWavePciStream
title : IPortWavePciStream
author : windows-driver-content
description : The IPortWavePciStream interface is the stream-associated callback interface that provides mapping services to WavePci miniport stream objects.
old-location : audio\iportwavepcistream.htm
old-project : audio
ms.assetid : c59ea7d7-17f1-4751-a948-387d7568b832
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audio.iportwavepcistream, IPortWavePciStream interface [Audio Devices], IPortWavePciStream interface [Audio Devices], described, IPortWavePciStream, portcls/IPortWavePciStream, audmp-routines_2ccb79d5-48b9-4b7b-8656-0d427ae99c22.xml
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IPortWavePciStream interface

The <code>IPortWavePciStream</code> interface is the stream-associated callback interface that provides mapping services to WavePci miniport stream objects. The WavePci port driver implements this interface and exposes it to the miniport driver. The port driver provides a reference to an <code>IPortWavePciStream</code> object to each miniport stream object that it creates. <code>IPortWavePciStream</code> inherits from the <b>IUnknown</b> interface.

The stream is associated with a pin on the WavePci filter, which the adapter driver forms by binding the port and miniport drivers. The port driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a> method to create the miniport stream object; the port driver passes an <code>IPortWavePciStream</code> reference as one of the call parameters.

## Methods

<p>The <b>IPortWavePciStream</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [portcls.IPortWavePciStream.GetMapping](nf-portcls-iportwavepcistream-getmapping.md) | The GetMapping method obtains a mapping from the port driver and associates a tag with the mapping. |
| [portcls.IPortWavePciStream.ReleaseMapping](nf-portcls-iportwavepcistream-releasemapping.md) | The ReleaseMapping method releases a mapping that was obtained by a previous call to IPortWavePciStream::GetMapping. |
| [portcls.IPortWavePciStream.TerminatePacket](nf-portcls-iportwavepcistream-terminatepacket.md) | The TerminatePacket method terminates the packet currently being mapped. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | portcls.h |