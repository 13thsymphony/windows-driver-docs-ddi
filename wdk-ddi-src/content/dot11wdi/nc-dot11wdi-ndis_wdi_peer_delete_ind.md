---
UID : NC:dot11wdi.NDIS_WDI_PEER_DELETE_IND
title : NDIS_WDI_PEER_DELETE_IND
author : windows-driver-content
description : The NdisWdiPeerDeleteIndication callback function initiates the removal of the association of between a peer ID and a peer MAC address.
old-location : netvista\ndiswdipeerdeleteindication.htm
old-project : netvista
ms.assetid : A13F2A98-BADA-43B8-A24B-0749C5558C35
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _SYNTH_STATS, SYNTH_STATS, *PSYNTH_STATS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : dot11wdi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NdisWdiPeerDeleteIndication
req.alt-loc : dot11wdi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : SYNTH_STATS, *PSYNTH_STATS
---


# NDIS_WDI_PEER_DELETE_IND callback function
The 
  NdisWdiPeerDeleteIndication callback function initiates the removal of the association of between a peer ID and a peer MAC address. Once this indication is processed, the peer ID can no longer be used  in subsequent Rx indications and the IHV may not inject any Tx frames for this peer.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.

## Syntax

```
NDIS_WDI_PEER_DELETE_IND NdisWdiPeerDeleteInd;

void NdisWdiPeerDeleteInd(
  NDIS_HANDLE NdisMiniportDataPathHandle,
  WDI_PORT_ID PortId,
  WDI_PEER_ID PeerId,
  NDIS_STATUS *pWifiStatus
)
{...}
```

## Parameters

`NdisMiniportDataPathHandle`

The NdisMiniportDataPathHandle passed to IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.

`PortId`

The port ID.

`PeerId`

The peer ID.

`*pWifiStatus`




## Return Value

This callback function does not return a value.

## Remarks

In PeerQueueing mode, the TxMgr issues a TxAbort for the peer.  If the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_abort.md">MiniportWdiTxAbort</a> completes synchronously and there are no outstanding TX frames for that peer, WDI_STATUS is set to NDIS_STATUS_SUCCESS and the peer deletion is complete (see <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm.md">MiniportWdiTalTxRxPeerDeleteConfirm</a> for  the description of a peer delete completion).  Otherwise, WDI issues a <i>MiniportWdiTalTxRxPeerDeleteConfirm</i> when the TxAbort is completed and there are no outstanding frames for this peer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dot11wdi.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>
</dt>
<dt>
<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>
</dt>
<dt>
<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm.md">MiniportWdiTalTxRxPeerDeleteConfirm</a>
</dt>
<dt>
<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_abort.md">MiniportWdiTxAbort</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_PEER_DELETE_IND callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>