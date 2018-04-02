---
UID: NC:dot11wdi.NDIS_WDI_TX_TRANSFER_COMPLETE_IND
title: NDIS_WDI_TX_TRANSFER_COMPLETE_IND
author: windows-driver-content
description: The NdisWdiTxTransferCompleteIndication callback function specifies a list of frame buffers that have been transferred to the target. Frames with different TX Status values are completed in separate indications.
old-location: netvista\ndiswditxtransfercompleteindication.htm
old-project: netvista
ms.assetid: BC66C993-F571-4EB9-8163-65B038ECE754
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_WDI_TX_TRANSFER_COMPLETE_IND, NdisWdiTxTransferCompleteIndication, NdisWdiTxTransferCompleteIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxTransferCompleteIndication, netvista.ndiswditxtransfercompleteindication
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
-	NdisWdiTxTransferCompleteIndication
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# NDIS_WDI_TX_TRANSFER_COMPLETE_IND callback function
The NdisWdiTxTransferCompleteIndication callback function specifies a list of frame buffers that have been transferred to the target.
Frames with different TX Status values are completed in separate indications.

If the TX status is a failure code, an <a href="https://msdn.microsoft.com/A38BA15D-FDD8-41D1-87ED-2CABC1926962">NdisWdiTxSendCompleteIndication</a> is not indicated for any of the frames in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> (NBL) chain.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.

## Syntax

```
NDIS_WDI_TX_TRANSFER_COMPLETE_IND NdisWdiTxTransferCompleteInd;

void NdisWdiTxTransferCompleteInd(
  NDIS_HANDLE NdisMiniportDataPathHandle,
  WDI_TX_FRAME_STATUS WifiTxFrameStatus,
  PNET_BUFFER_LIST pNBL
)
{...}
```

## Parameters

`NdisMiniportDataPathHandle`

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.

`WifiTxFrameStatus`

The TX status, specified as a <a href="https://msdn.microsoft.com/library/windows/hardware/dn898194">WDI_TX_FRAME_STATUS</a> value.

`pNBL`

The null-terminated list of frame buffers that have been transferred to the target.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/A38BA15D-FDD8-41D1-87ED-2CABC1926962">NdisWdiTxSendCompleteIndication</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898194">WDI_TX_FRAME_STATUS</a>