---
UID: NC:dot11wdi.NDIS_WDI_RX_STOP_CONFIRM
title: NDIS_WDI_RX_STOP_CONFIRM
author: windows-driver-content
description: The NdisWdiRxStopConfirm callback function indicates completion of a MiniportWdiRxStop request.
old-location: netvista\ndiswdirxstopconfirm.htm
old-project: netvista
ms.assetid: 2022915A-2717-4098-BCD8-34130A161967
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_WDI_RX_STOP_CONFIRM, NdisWdiRxStopConfirm, NdisWdiRxStopConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiRxStopConfirm, netvista.ndiswdirxstopconfirm
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
-	NdisWdiRxStopConfirm
product:
- Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# NDIS_WDI_RX_STOP_CONFIRM callback function
The 
  NdisWdiRxStopConfirm callback function indicates completion of a <a href="https://msdn.microsoft.com/AAFECA64-07D7-43E6-ABFB-C0C85A9C03CD">MiniportWdiRxStop</a> request.  If traffic is stopped across the entire adapter, the target must stop indicating frames that match the stop request to the host prior to issuing  <b>NdisWdiRxStopConfirm</b>.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.

## Syntax

```
NDIS_WDI_RX_STOP_CONFIRM NdisWdiRxStopConfirm;

void NdisWdiRxStopConfirm(
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

<a href="https://msdn.microsoft.com/AAFECA64-07D7-43E6-ABFB-C0C85A9C03CD">MiniportWdiRxStop</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>