---
UID: NC:dot11wdi.MINIPORT_WDI_RX_STOP
title: MINIPORT_WDI_RX_STOP
author: windows-driver-content
description: The MiniportWdiRxStop handler function stops RX on a given port and accepts the wildcard port ID to stop RX across the adapter.
old-location: netvista\miniportwdirxstop.htm
old-project: netvista
ms.assetid: AAFECA64-07D7-43E6-ABFB-C0C85A9C03CD
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MINIPORT_WDI_RX_STOP, MiniportWdiRxStop, MiniportWdiRxStop callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxStop, netvista.miniportwdirxstop
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
-	MiniportWdiRxStop
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_RX_STOP callback function
The 
  MiniportWdiRxStop handler function stops RX on a given port and accepts the wildcard port ID  to stop RX across the adapter. The TAL completes the RX stop operation by completing the request with a success status, or by completing it with a pending status and asynchronously indicating <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_rx_stop_confirm.md">RxStopConfirm</a>.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.

Prior to completing the indication, the target must be configured to stop indicating new traffic on the selected port or the entire adapter.

This request is issued to the TAL as part of a transition to low power (adapter) and dot11 reset (port).
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_STOP</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_WDI_RX_STOP MiniportWdiRxStop;

void MiniportWdiRxStop(
  TAL_TXRX_HANDLE MiniportTalTxRxContext,
  WDI_PORT_ID PortId,
  NDIS_STATUS *pWifiStatus
)
{...}
```

## Parameters

`MiniportTalTxRxContext`

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.

`PortId`

The port ID.

`*pWifiStatus`

Status from the IHV miniport. A success status indicates that the operation completion synchronously.  A pending status indicates that the stop will be asynchronously confirmed.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_RX_STOP callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>