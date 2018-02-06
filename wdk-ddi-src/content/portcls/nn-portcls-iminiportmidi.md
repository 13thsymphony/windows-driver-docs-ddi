---
UID: NN:portcls.IMiniportMidi
title: IMiniportMidi
author: windows-driver-content
description: The IMiniportMidi interface is the primary interface for a MIDI miniport driver for a MIDI synthesizer device.
old-location: audio\iminiportmidi.htm
old-project: audio
ms.assetid: 42170a24-377c-4cc5-962e-97ed74302d63
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.iminiportmidi, IMiniportMidi interface [Audio Devices], IMiniportMidi interface [Audio Devices], described, IMiniportMidi, portcls/IMiniportMidi, audmp-routines_bba7ae00-6719-49dd-9770-9292a96f42ec.xml
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
-	IMiniportMidi
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IMiniportMidi interface

The <code>IMiniportMidi</code> interface is the primary interface for a MIDI miniport driver for a MIDI synthesizer device. The MIDI port driver communicates with the miniport driver through this interface. The adapter driver creates the MIDI miniport object and passes the object's <code>IMiniportMidi</code> interface pointer to the MIDI port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a> method (see the code example in <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a>). <code>IMiniportMidi</code> inherits from the <a href="..\portcls\nn-portcls-iminiport.md">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportMidi</code> object to an <a href="..\portcls\nn-portcls-iportmidi.md">IPortMidi</a> object. The PortCls system driver registers this pair with the system as a MIDI filter (see <a href="https://msdn.microsoft.com/622aa4ae-c855-4088-bc1a-30dff7a24d23">MIDI and DirectMusic Filters</a>).

The <code>IMiniportMidi</code> interface provides methods for initializing the miniport object, for creating a new MIDI stream, and for notifying the miniport driver of an interrupt service request.

## Methods

<p>The <b>IMiniportMidi</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [portcls.IMiniportMidi.Init](nf-portcls-iminiportmidi-init.md) | The Init method initializes the MIDI miniport object. |
| [portcls.IMiniportMidi.NewStream](nf-portcls-iminiportmidi-newstream.md) | The NewStream method creates a new instance of a logical stream associated with a specified physical channel. |
| [portcls.IMiniportMidi.Service](nf-portcls-iminiportmidi-service.md) | The Service method notifies the miniport driver of a request for service. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | portcls.h |