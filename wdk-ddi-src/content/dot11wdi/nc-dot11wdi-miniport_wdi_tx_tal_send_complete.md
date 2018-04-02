---
UID: NC:dot11wdi.MINIPORT_WDI_TX_TAL_SEND_COMPLETE
title: MINIPORT_WDI_TX_TAL_SEND_COMPLETE
author: windows-driver-content
description: The MiniportWdiTxTalSendComplete handler function returns ownership of one or more TX frame injected by the TAL back to the TxEngine.
old-location: netvista\miniportwditxtalsendcomplete.htm
old-project: netvista
ms.assetid: 347B069F-76B6-42D5-9613-7D0214C2FEDB
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: MINIPORT_WDI_TX_TAL_SEND_COMPLETE, MiniportWdiTxTalSendComplete, MiniportWdiTxTalSendComplete callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTxTalSendComplete, netvista.miniportwditxtalsendcomplete
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
-	MiniportWdiTxTalSendComplete
product:
- Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_TX_TAL_SEND_COMPLETE callback function
The 
  MiniportWdiTxTalSendComplete handler function returns ownership of one or more TX frame injected by the TAL back to the TxEngine. The TxMgr uses this interface to return a frame after receiving the corresponding transfer and TX completion (if applicable). Frames completed with different frame statuses are returned in separate requests.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_TAL_SEND_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_WDI_TX_TAL_SEND_COMPLETE MiniportWdiTxTalSendComplete;

void MiniportWdiTxTalSendComplete(
  TAL_TXRX_HANDLE MiniportTalTxRxContext,
  PNET_BUFFER_LIST pNBL,
  WDI_TX_FRAME_STATUS TxFrameStatus
)
{...}
```

## Parameters

`MiniportTalTxRxContext`

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.

`pNBL`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> chain.

`TxFrameStatus`

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn898194">WDI_TX_FRAME_STATUS</a> enumeration value that specifies the TX frame status.


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898194">WDI_TX_FRAME_STATUS</a>