---
UID: NC:dot11wdi.MINIPORT_WDI_TX_PEER_BACKLOG
title: MINIPORT_WDI_TX_PEER_BACKLOG
author: windows-driver-content
description: The MiniportWdiTxPeerBacklog handler function is issued when a paused peer has a change in backlog state.
old-location: netvista\miniportwditxpeerbacklog.htm
old-project: netvista
ms.assetid: 49DC9034-9A50-4B0F-B7F7-A06147D1046F
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: MINIPORT_WDI_TX_PEER_BACKLOG, MiniportWdiTxPeerBacklog, MiniportWdiTxPeerBacklog callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTxPeerBacklog, netvista.miniportwditxpeerbacklog
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dot11wdi.h
api_name:
-	MiniportWdiTxPeerBacklog
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_TX_PEER_BACKLOG callback function
The 
  MiniportWdiTxPeerBacklog handler function is issued when a paused peer has a change in backlog state.  This can happen when WDI receives a send request or as a result of an <a href="https://msdn.microsoft.com/1324D516-8AEF-4357-86EC-81F6EBDC8FB9">NdisWdiTxReleaseFrameIndication</a>.  It is also issued on an <a href="https://msdn.microsoft.com/A8001D08-36B8-4557-A763-103BDC807CA4">NdisWdiTxSendPauseIndication</a> for affected peers to notify the IHV miniport of the backlog states of those peers.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.

This request is never made when <b>TargetPriorityQueueing</b> is set to true.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_PEER_BACKLOG</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_WDI_TX_PEER_BACKLOG MiniportWdiTxPeerBacklog;

void MiniportWdiTxPeerBacklog(
  TAL_TXRX_HANDLE MiniportTalTxRxContext,
  WDI_PORT_ID PortId,
  WDI_PEER_ID PeerId,
  BOOLEAN bBacklogged
)
{...}
```

## Parameters

`MiniportTalTxRxContext`

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.

`PortId`

The port ID.

`PeerId`

The peer ID.

`bBacklogged`

The backlog state.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/1324D516-8AEF-4357-86EC-81F6EBDC8FB9">NdisWdiTxReleaseFrameIndication</a>



<a href="https://msdn.microsoft.com/A8001D08-36B8-4557-A763-103BDC807CA4">NdisWdiTxSendPauseIndication</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898187">WDI_TXRX_CAPABILITIES</a>