---
UID: NN.portcls.IMiniportPnpNotify
title: IMiniportPnpNotify
author: windows-driver-content
description: IMiniportPnpNotify is an optional interface to allow miniport objects (audio subdevices) to receive PnP state change notifications.
old-location: audio\iminiportpnpnotify.htm
old-project: audio
ms.assetid: 634ADB7C-85B6-4C37-81A0-4A4891D0BBC4
ms.author: windowsdriverdev
ms.date: 12/6/2017
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
req.alt-api: IMiniportPnpNotify
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
---

# IMiniportPnpNotify interface



## -description
IMiniportPnpNotify is an optional interface to allow miniport objects (audio subdevices)  to receive PnP state change notifications.


IMiniportPnpNotify interface available is on both WaveRT and Topology.

Miniports have an opportunity to receive a PnP Stop notification for each audio subdevice they have registered. To receive this notification, the subdevice must support IMiniportPnpNotify.
 Only the <a href="audio.iminiportpnpnotify_pnpstop">IMiniportPnpNotify::PnpStop</a> notification is defined on this interface.

IAdapterPnpManagement is available in Windows 10, version 1511 and later versions of Windows. 

For more information, see <a href="https://msdn.microsoft.com/FCAD7F8B-AA9B-430A-BCAF-04E13FA15382">
Implement PnP Rebalance for PortCls Audio Drivers</a>.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportPnpNotify</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.


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