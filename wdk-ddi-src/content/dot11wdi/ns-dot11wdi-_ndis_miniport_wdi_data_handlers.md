---
UID: NS:dot11wdi._NDIS_MINIPORT_WDI_DATA_HANDLERS
title: "_NDIS_MINIPORT_WDI_DATA_HANDLERS"
author: windows-driver-content
description: The NDIS_MINIPORT_WDI_DATA_HANDLERS structure specifies the entry points for the IHV miniport datapath handlers.
old-location: netvista\ndis_miniport_wdi_data_handlers.htm
old-project: netvista
ms.assetid: DBDB5F08-9988-4D9B-A731-DA65BBA67813
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_MINIPORT_WDI_DATA_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], dot11wdi/NDIS_MINIPORT_WDI_DATA_HANDLERS, NDIS_MINIPORT_WDI_DATA_HANDLERS structure [Network Drivers Starting with Windows Vista], dot11wdi/PNDIS_MINIPORT_WDI_DATA_HANDLERS, _NDIS_MINIPORT_WDI_DATA_HANDLERS, NDIS_MINIPORT_WDI_DATA_HANDLERS, PNDIS_MINIPORT_WDI_DATA_HANDLERS, netvista.ndis_miniport_wdi_data_handlers, *PNDIS_MINIPORT_WDI_DATA_HANDLERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: Ndis.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dot11wdi.h
apiname:
-	NDIS_MINIPORT_WDI_DATA_HANDLERS
product: Windows
targetos: Windows
req.typenames: "*PNDIS_MINIPORT_WDI_DATA_HANDLERS, NDIS_MINIPORT_WDI_DATA_HANDLERS"
---

# _NDIS_MINIPORT_WDI_DATA_HANDLERS structure
The NDIS_MINIPORT_WDI_DATA_HANDLERS structure specifies the entry points for the IHV miniport datapath handlers.

## Syntax
````
typedef struct _NDIS_MINIPORT_WDI_DATA_HANDLERS {
  NDIS_OBJECT_HEADER                                Header;
  MINIPORT_WDI_TX_ABORT_HANDLER                     TxAbortHandler;
  MINIPORT_WDI_TX_TARGET_DESC_INIT_HANDLER          TxTargetDescInitHandler;
  MINIPORT_WDI_TX_TARGET_DESC_DEINIT_HANDLER        TxTargetDescDeInitHandler;
  MINIPORT_WDI_TX_DATA_SEND_HANDLER                 TxDataSendHandler;
  MINIPORT_WDI_TX_TAL_SEND_HANDLER                  TxTalSendHandler;
  MINIPORT_WDI_TX_TAL_SEND_COMPLETE_HANDLER         TxTalSendCompleteHandler;
  MINIPORT_WDI_TX_TAL_QUEUE_IN_ORDER_HANDLER        TxTalQueueInOrderHandler;
  MINIPORT_WDI_TX_PEER_BACKLOG_HANDLER              TxPeerBacklogHandler;
  MINIPORT_WDI_RX_STOP_HANDLER                      RxStopHandler;
  MINIPORT_WDI_RX_FLUSH_HANDLER                     RxFlushHandler;
  MINIPORT_WDI_RX_RESTART_HANDLER                   RxRestartHandler;
  MINIPORT_WDI_RX_GET_MPDUS_HANDLER                 RxGetMpdusHandler;
  MINIPORT_WDI_RX_RETURN_FRAMES_HANDLER             RxReturnFramesHandler;
  MINIPORT_WDI_RX_RESUME_HANDLER                    RxResumeHandler;
  MINIPORT_WDI_RX_THROTTLE_HANDLER                  RxThrottleHandler;
  MINIPORT_WDI_RX_PPDU_RSSI_HANDLER                 RxPpduRssiHandler;
  MINIPORT_WDI_TAL_TXRX_START_HANDLER               TalTxRxStartHandler;
  MINIPORT_WDI_TAL_TXRX_STOP_HANDLER                TalTxRxStopHandler;
  MINIPORT_WDI_TAL_TXRX_ADD_PORT_HANDLER            TalTxRxAddPortHandler;
  MINIPORT_WDI_TAL_TXRX_DELETE_PORT_HANDLER         TalTxRxDeletePortHandler;
  MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE_HANDLER     TalTxRxSetPortOpModeHandler;
  MINIPORT_WDI_TAL_TXRX_RESET_PORT_HANDLER          TalTxRxResetPortHandler;
  MINIPORT_WDI_TAL_TXRX_PEER_CONFIG_HANDLER         TalTxRxPeerConfigHandler;
  MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM_HANDLER TalTxRxPeerDeleteConfirmHandler;
} NDIS_MINIPORT_WDI_DATA_HANDLERS, *PNDIS_MINIPORT_WDI_DATA_HANDLERS;
````

## Members


`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_WDI_DATA_HANDLERS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_WDI_DATA_HANDLERS.
     

To indicate the version of the NDIS_MINIPORT_WDI_DATA_HANDLERS structure, set the 
     <b>Revision</b> member to the following value:





#### NDIS_OBJECT_TYPE_MINIPORT_WDI_DATA_HANDLERS_REVISION_1

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_WDI_DATA_HANDLERS_REVISION_1.

`RxFlushHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_flush.md">MiniportWdiRxFlush</a> handler function.

`RxGetMpdusHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_get_mpdus.md">MiniportWdiRxGetMpdus</a> handler function.

`RxPpduRssiHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_ppdu_rssi.md">MiniportWdiRxPpduRssi</a> handler function.

`RxRestartHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_restart.md">MiniportWdiRxRestart</a> handler function.

`RxResumeHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_resume.md">MiniportWdiRxResume</a> handler function.

`RxReturnFramesHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_return_frames.md">MiniportWdiRxReturnFrames</a> handler function.

`RxStopHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_stop.md">MiniportWdiRxStop</a> handler function.

`RxThrottleHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_throttle.md">MiniportWdiRxThrottle</a> handler function.

`TalTxRxAddPortHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_add_port.md">MiniportWdiTalTxRxAddPort</a> handler function.

`TalTxRxDeletePortHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_delete_port.md">MiniportWdiTalTxRxDeletePort</a> handler function.

`TalTxRxPeerConfigHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_peer_config.md">MiniportWdiTalTxRxPeerConfig</a> handler function.

`TalTxRxPeerDeleteConfirmHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_peer_delete_confirm.md">MiniportWdiTalTxRxPeerDeleteConfirm</a> handler function.

`TalTxRxResetPortHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_reset_port.md">MiniportWdiTalTxRxResetPort</a> handler function.

`TalTxRxSetPortOpModeHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_set_port_opmode.md">MiniportWdiTalTxRxSetPortOpMode</a> handler function.

`TalTxRxStartHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_start.md">MiniportWdiTalTxRxStart</a> handler function.

`TalTxRxStopHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_stop.md">MiniportWdiTalTxRxStop</a> handler function.

`TxAbortHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_abort.md">MiniportWdiTxAbort</a> handler function.

`TxDataSendHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_data_send.md">MiniportWdiTxDataSend</a> handler function.

`TxPeerBacklogHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_peer_backlog.md">MiniportWdiTxPeerBacklog</a> handler function.

`TxSuspectFrameAbortHandler`



`TxTalQueueInOrderHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order.md">MiniportWdiTxTalQueueInOrder</a> handler function.

`TxTalSendCompleteHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_send_complete.md">MiniportWdiTxTalSendComplete</a> handler function.

`TxTalSendHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_send.md">MiniportWdiTxTalSend</a> handler function.

`TxTargetDescDeInitHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_target_desc_deinit.md">MiniportWdiTxTargetDescDeInit</a> handler function.

`TxTargetDescInitHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_target_desc_init.md">MiniportWdiTxTargetDescInit</a> handler function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h (include Ndis.h) |