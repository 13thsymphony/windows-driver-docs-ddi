---
UID: NC:dot11wdi.MINIPORT_WDI_RX_RETURN_FRAMES
title: MINIPORT_WDI_RX_RETURN_FRAMES
author: windows-driver-content
description: The MiniportWdiRxReturnFrames handler function returns a NET_BUFFER_LIST structure (and associated data buffers) to the TAL.
old-location: netvista\miniportwdirxreturnframes.htm
old-project: netvista
ms.assetid: BF2DB7C6-97F9-454B-8DED-E8CC21A4F07F
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: MINIPORT_WDI_RX_RETURN_FRAMES, MiniportWdiRxReturnFrames, MiniportWdiRxReturnFrames callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxReturnFrames, netvista.miniportwdirxreturnframes
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
-	MiniportWdiRxReturnFrames
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_RX_RETURN_FRAMES callback function
The 
  MiniportWdiRxReturnFrames handler function returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure (and associated data buffers) to the TAL.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_RETURN_FRAMES</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_WDI_RX_RETURN_FRAMES MiniportWdiRxReturnFrames;

void MiniportWdiRxReturnFrames(
  TAL_TXRX_HANDLE MiniportTalTxRxContext,
  PNET_BUFFER_LIST pNBL
)
{...}
```

## Parameters

`MiniportTalTxRxContext`

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.

`pNBL`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> chain being returned to the IHV miniport.


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



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>