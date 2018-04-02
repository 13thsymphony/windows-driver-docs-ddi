---
UID: NC:dot11wdi.NDIS_WDI_RX_FLUSH_CONFIRM
title: NDIS_WDI_RX_FLUSH_CONFIRM
author: windows-driver-content
description: The NdisWdiRxFlushConfirm callback function indicates completion of a MiniportWdiRxFlush request. The RxEngine must complete the discard of all RX data frames that match the flush request prior to issuing NdisWdiRxFlushConfirm.
old-location: netvista\ndiswdirxflushconfirm.htm
old-project: netvista
ms.assetid: CEED709C-F295-4633-B7C1-4719EDDC7CD4
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_WDI_RX_FLUSH_CONFIRM, NdisWdiRxFlushConfirm, NdisWdiRxFlushConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiRxFlushConfirm, netvista.ndiswdirxflushconfirm
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
-	NdisWdiRxFlushConfirm
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# NDIS_WDI_RX_FLUSH_CONFIRM callback function
The NdisWdiRxFlushConfirm callback function indicates completion of a <a href="https://msdn.microsoft.com/76945A84-A6DB-4753-B04E-32249359B8C6">MiniportWdiRxFlush</a> request. The RxEngine must complete the discard of all RX data frames that match the flush request prior to issuing <i>NdisWdiRxFlushConfirm</i>.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.

## Syntax

```
NDIS_WDI_RX_FLUSH_CONFIRM NdisWdiRxFlushConfirm;

void NdisWdiRxFlushConfirm(
  NDIS_HANDLE NdisMiniportDataPathHandle
)
{...}
```

## Parameters

`NdisMiniportDataPathHandle`

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="https://msdn.microsoft.com/76945A84-A6DB-4753-B04E-32249359B8C6">MiniportWdiRxFlush</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>