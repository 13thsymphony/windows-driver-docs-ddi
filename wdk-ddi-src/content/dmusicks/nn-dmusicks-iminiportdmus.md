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
ms.keywords: audio.iminiportdmus, IMiniportDMus interface [Audio Devices], IMiniportDMus interface [Audio Devices], described, IMiniportDMus, dmusicks/IMiniportDMus, audmp-routines_b123c50b-e4b9-4f19-a2c4-b33fb335bec6.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dmusicks.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dmusicks.h
apiname:
-	IMiniportDMus
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# IMiniportDMus interface

The <code>IMiniportDMus</code> interface is the primary interface for a DMus miniport driver for a DirectMusic synthesizer device. The DMus port driver communicates with the miniport driver through this interface. The adapter driver creates the DMus miniport object and passes the object's <code>IMiniportDMus</code> interface pointer to the port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a> method (see the code example in <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a>). <code>IMiniportDMus</code> inherits from the <a href="..\portcls\nn-portcls-iminiport.md">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportDMus</code> object to an <a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a> object. The PortCls system driver registers this pair with the system as a DirectMusic filter (see <a href="https://msdn.microsoft.com/622aa4ae-c855-4088-bc1a-30dff7a24d23">MIDI and DirectMusic Filters</a>).

The <code>IMiniportDMus</code> interface provides methods for initializing the miniport driver, for creating a new DirectMusic stream, and for notifying the miniport driver of an interrupt service request.

## Methods

<p>The <b>IMiniportDMus</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [dmusicks.IMiniportDMus.Init](nf-dmusicks-iminiportdmus-init.md) | The Init method initializes the DMus miniport object. |
| [dmusicks.IMiniportDMus.NewStream](nf-dmusicks-iminiportdmus-newstream.md) | The NewStream method creates a new instance of a logical stream associated with a specified physical channel. |
| [dmusicks.IMiniportDMus.Service](nf-dmusicks-iminiportdmus-service.md) | This method does not currently need to be implemented in the miniport driver. The Service method is currently unused. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dmusicks.h (include Dmusicks.h) |