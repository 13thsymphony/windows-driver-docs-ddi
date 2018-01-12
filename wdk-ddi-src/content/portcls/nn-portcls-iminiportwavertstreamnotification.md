---
UID: NN:portcls.IMiniportWaveRTStreamNotification
title: IMiniportWaveRTStreamNotification
author: windows-driver-content
description: The IMiniportWaveRTStreamNotification interface is supported in Windows Vista and later Windows operating systems, and it augments the IMiniportWaveRTStream interface, providing additional methods to facilitate DMA driver event notifications.
old-location: audio\iminiportwavertstreamnotification.htm
old-project: audio
ms.assetid: e009c459-77f7-43ee-9e95-8408324b0a9b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcUnregisterIoTimeout
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
req.alt-api: IMiniportWaveRTStreamNotification
req.alt-loc: portcls.h
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
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IMiniportWaveRTStreamNotification interface



## -description
The <code>IMiniportWaveRTStreamNotification</code> interface is supported in Windows Vista and later Windows operating systems, and it augments the <a href="..\portcls\nn-portcls-iminiportwavertstream.md">IMiniportWaveRTStream</a> interface, providing additional methods to facilitate DMA driver event notifications. 

To access the <code>IMiniportWaveRTStreamNotification</code> interface, the <a href="https://msdn.microsoft.com/d25e37e2-2e29-4bf9-8150-221ebef88c87">WaveRT port driver</a> calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536762">IMiniportWaveRT::NewStream</a> method and receives an <a href="..\portcls\nn-portcls-iminiportwavertstream.md">IMiniportWaveRTStream</a> interface. The WaveRT port driver then queries the <b>IMiniportWaveRTStream</b> interface, uisng QueryInterface, and receives the <code>IMiniportWaveRTStreamNotification</code> interface. 

<code>IMiniportWaveRTStreamNotification</code> inherits from the <b>IUnknown</b> interface.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportWaveRTStreamNotification</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
</table>