---
UID: NC:dot11wdi.MINIPORT_WDI_TX_PEER_BACKLOG
title: MINIPORT_WDI_TX_PEER_BACKLOG
author: windows-driver-content
description: The MiniportWdiTxPeerBacklog handler function is issued when a paused peer has a change in backlog state.
old-location: netvista\miniportwditxpeerbacklog.htm
old-project: netvista
ms.assetid: 49DC9034-9A50-4B0F-B7F7-A06147D1046F
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwditxpeerbacklog, MiniportWdiTxPeerBacklog callback function [Network Drivers Starting with Windows Vista], MiniportWdiTxPeerBacklog, MINIPORT_WDI_TX_PEER_BACKLOG, MINIPORT_WDI_TX_PEER_BACKLOG, dot11wdi/MiniportWdiTxPeerBacklog
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dot11wdi.h
apiname:
-	MiniportWdiTxPeerBacklog
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_TX_PEER_BACKLOG callback function
The 
  MiniportWdiTxPeerBacklog handler function is issued when a paused peer has a change in backlog state.  This can happen when WDI receives a send request or as a result of an <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_release_frames_ind.md">NdisWdiTxReleaseFrameIndication</a>.  It is also issued on an <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a> for affected peers to notify the IHV miniport of the backlog states of those peers.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.

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

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.

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
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="..\dot11wdi\ns-dot11wdi-_wdi_txrx_target_capabilities.md">WDI_TXRX_CAPABILITIES</a>

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>

<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a>

<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_release_frames_ind.md">NdisWdiTxReleaseFrameIndication</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TX_PEER_BACKLOG callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>