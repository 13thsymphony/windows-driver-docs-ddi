---
UID: NN:portcls.IMiniportWaveRTStream
title: IMiniportWaveRTStream
author: windows-driver-content
description: The IMiniportWaveRTStream interface represents the wave stream that flows through a pin on the KS filter that wraps a WaveRT rendering or capture device.
old-location: audio\iminiportwavertstream.htm
old-project: audio
ms.assetid: be398a37-0329-411b-ba41-a03dbc5f72a1
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.iminiportwavertstream, IMiniportWaveRTStream interface [Audio Devices], IMiniportWaveRTStream interface [Audio Devices], described, IMiniportWaveRTStream, portcls/IMiniportWaveRTStream, audmp-routines_9f8c9dbe-8e68-4b7b-b2de-b409d77f15d6.xml
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
-	IMiniportWaveRTStream
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IMiniportWaveRTStream interface

The <code>IMiniportWaveRTStream</code> interface represents the wave stream that flows through a pin on the KS filter that wraps a WaveRT rendering or capture device. The miniport driver implements the <code>IMiniportWaveRTStream</code> interface and exposes it to the port driver. The miniport driver creates a stream object with this interface when the port driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536762">IMiniportWaveRT::NewStream</a> method. <code>IMiniportWaveRTStream</code> inherits from the <b>IUnknown</b> interface.

<code>IMiniportWaveRTStream</code> is supported in Windows Vista and later Windows operating systems.

## Methods

<p>The <b>IMiniportWaveRTStream</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | portcls.h |