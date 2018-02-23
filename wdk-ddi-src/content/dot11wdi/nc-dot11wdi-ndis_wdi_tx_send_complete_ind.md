---
UID: NC:dot11wdi.NDIS_WDI_TX_SEND_COMPLETE_IND
title: NDIS_WDI_TX_SEND_COMPLETE_IND
author: windows-driver-content
description: The NdisWdiTxSendCompleteIndication callback function specifies an array of frame IDs associated with the target's sent frames.
old-location: netvista\ndiswditxsendcompleteindication.htm
old-project: netvista
ms.assetid: A38BA15D-FDD8-41D1-87ED-2CABC1926962
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ndiswditxsendcompleteindication, NdisWdiTxSendCompleteIndication callback function [Network Drivers Starting with Windows Vista], NdisWdiTxSendCompleteIndication, NDIS_WDI_TX_SEND_COMPLETE_IND, NDIS_WDI_TX_SEND_COMPLETE_IND, dot11wdi/NdisWdiTxSendCompleteIndication
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
-	NdisWdiTxSendCompleteIndication
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_STATS, SYNTH_STATS"
---


# NDIS_WDI_TX_SEND_COMPLETE_IND callback function
The NdisWdiTxSendCompleteIndication callback function specifies an array of frame IDs associated with the target's sent frames.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.

Frames with different TX status values are completed in separate indications.

## Syntax

```
NDIS_WDI_TX_SEND_COMPLETE_IND NdisWdiTxSendCompleteInd;

void NdisWdiTxSendCompleteInd(
  NDIS_HANDLE NdisMiniportDataPathHandle,
  WDI_TX_FRAME_STATUS WifiTxFrameStatus,
  UINT16 NumCompletedSends,
  WDI_FRAME_ID *WifiTxFrameIdList,
  WDI_TX_COMPLETE_DATA *WifiTxCompleteList
)
{...}
```

## Parameters

`NdisMiniportDataPathHandle`

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.

`WifiTxFrameStatus`

The TX status, specified as a <a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_frame_status.md">WDI_TX_FRAME_STATUS</a> value.

`NumCompletedSends`

The number of completed sends.

`*WifiTxFrameIdList`

An array of frame IDs. The size of the array is the value of <i>NumCompletedSends</i>.

`*WifiTxCompleteList`

An array of TX completion data. The size of the array is the value of <i>NumCompletedSends</i>.


## Return Value

This callback function does not return a value.

## Remarks

<a href="..\dot11wdi\ns-dot11wdi-_wdi_tx_complete_data.md">WDI_TX_COMPLETE_DATA</a> is optional for all status values unless the indicated frames are sent over-the-air and have a status of <b>WDI_TxFrameStatus_SendPostponed</b>. In that case, <b>WDI_TX_COMPLETE_DATA</b> is required.

A TX completion with a frame with <b>WDI_TxFrameStatus_SendPostponed</b> is identical to an <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a> with <b>WDI_TX_PAUSE_REASON_PS</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_frame_status.md">WDI_TX_FRAME_STATUS</a>



<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a>



<a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_pause_reason.md">WDI_TX_PAUSE_REASON</a>



<a href="..\dot11wdi\ns-dot11wdi-_wdi_tx_complete_data.md">WDI_TX_COMPLETE_DATA</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_TX_SEND_COMPLETE_IND callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>