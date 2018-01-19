---
UID : NS:dot11wdi._NDIS_WDI_DATA_API
title : _NDIS_WDI_DATA_API
author : windows-driver-content
description : The NDIS_WDI_DATA_API structure specifies the entry points for WDI data indications.
old-location : netvista\ndis_wdi_data_api.htm
old-project : netvista
ms.assetid : 8C26D62E-711A-4CE7-BD2B-D78B794C67FB
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_WDI_DATA_API, NDIS_WDI_DATA_API, *PNDIS_WDI_DATA_API
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dot11wdi.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_WDI_DATA_API
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
req.irql : PASSIVE_LEVEL
req.typenames : NDIS_WDI_DATA_API, *PNDIS_WDI_DATA_API
---

# _NDIS_WDI_DATA_API structure
The 
  NDIS_WDI_DATA_API structure specifies the entry points for WDI data indications.

## Syntax
````
typedef struct _NDIS_WDI_DATA_API {
  NDIS_OBJECT_HEADER                           Header;
  NDIS_WDI_TX_DEQUEUE_IND_HANDLER              TxDequeueIndication;
  NDIS_WDI_TX_TRANSFER_COMPLETE_IND_HANDLER    TxTransferCompleteIndication;
  NDIS_WDI_TX_SEND_COMPLETE_IND_HANDLER        TxSendCompleteIndication;
  NDIS_WDI_TX_QUERY_RA_TID_STATE_HANDLER       TxQueryRATIDState;
  NDIS_WDI_TX_SEND_PAUSE_IND_HANDLER           TxSendPauseIndication;
  NDIS_WDI_TX_SEND_RESTART_IND_HANDLER         TxSendRestartIndication;
  NDIS_WDI_TX_RELEASE_FRAMES_IND_HANDLER       TxReleaseFrameIndication;
  NDIS_WDI_TX_INJECT_FRAME_IND_HANDLER         TxInjectFrameIndication;
  NDIS_WDI_TX_ABORT_CONFIRM_HANDLER            TxAbortConfirm;
  NDIS_WDI_RX_INORDER_DATA_IND_HANDLER         RxInorderDataIndication;
  NDIS_WDI_RX_STOP_CONFIRM_HANDLER             RxStopConfirm;
  NDIS_WDI_RX_FLUSH_CONFIRM_HANDLER            RxFlushConfirm;
  NDIS_WDI_PEER_CREATE_IND_HANDLER             PeerCreateIndication;
  NDIS_WDI_PEER_DELETE_IND_HANDLER             PeerDeleteIndication;
  NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA_HANDLER AllocateWiFiFrameMetaData;
  NDIS_WDI_FREE_WDI_FRAME_METADATA_HANDLER     FreeWiFiFrameMetaData;
} NDIS_WDI_DATA_API, *PNDIS_WDI_DATA_API;
````

## Members

        
            `AllocateWiFiFrameMetaData`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_allocate_wdi_frame_metadata.md">NdisWdiAllocateWiFiFrameMetaData</a> callback function.
        
            `FreeWiFiFrameMetaData`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_free_wdi_frame_metadata.md">NdisWdiFreeWiFiFrameMetaData</a> callback function.
        
            `Header`

            The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_WDI_DATA_API structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_WDI_DATA_API.
     

To indicate the version of the NDIS_WDI_DATA_API structure, set the 
     <b>Revision</b> member to the following value:
        
            `PeerCreateIndication`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_peer_create_ind.md">NdisWdiPeerCreateIndication</a> callback function.
        
            `PeerDeleteIndication`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_peer_delete_ind.md">NdisWdiPeerDeleteIndication</a> callback function.
        
            `RxFlushConfirm`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_rx_flush_confirm.md">NdisWdiRxFlushConfirm</a> callback function.
        
            `RxInorderDataIndication`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_rx_inorder_data_ind.md">NdisWdiRxInorderDataIndication</a> callback function.
        
            `RxStopConfirm`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_rx_stop_confirm.md">NdisWdiRxStopConfirm</a> callback function.
        
            `TxAbortConfirm`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_abort_confirm.md">NdisWdiTxAbortConfirm</a> callback function.
        
            `TxDequeueIndication`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_dequeue_ind.md">NdisWdiTxDequeueIndication</a> callback function.
        
            `TxInjectFrameIndication`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_inject_frame_ind.md">NdisWdiTxInjectFrameIndication</a> callback function.
        
            `TxQueryRATIDState`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_query_ra_tid_state.md">NdisWdiTxQueryRATIDState</a> callback function.
        
            `TxReleaseFrameIndication`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_release_frames_ind.md">NdisWdiTxReleaseFrameIndication</a> callback function.
        
            `TxSendCompleteIndication`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_complete_ind.md">NdisWdiTxSendCompleteIndication</a> callback function.
        
            `TxSendPauseIndication`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a> callback function.
        
            `TxSendRestartIndication`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_restart_ind.md">NdisWdiTxSendRestartIndication</a> callback function.
        
            `TxTransferCompleteIndication`

            The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_transfer_complete_ind.md">NdisWdiTxTransferCompleteIndication</a> callback function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dot11wdi.h (include Ndis.h) |