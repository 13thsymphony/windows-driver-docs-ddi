---
UID: NC:dot11wdi.MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION
title: MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION
author: windows-driver-content
description: NDIS calls the MiniportWdiCancelIdleNotification handler function to notify the WDI miniport driver that NDIS has detected activity on the suspended network adapter.
old-location: netvista\miniportwdicancelidlenotification.htm
old-project: netvista
ms.assetid: 4C52E367-2E75-47EC-8743-F3FA2EEE25F8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION, MiniportWdiCancelIdleNotification, MiniportWdiCancelIdleNotification callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiCancelIdleNotification, netvista.miniportwdicancelidlenotification
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
-	MiniportWdiCancelIdleNotification
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION callback function
NDIS calls the MiniportWdiCancelIdleNotification handler function to notify the WDI miniport driver that NDIS has detected activity on the suspended network adapter. Because of this, NDIS cancels the idle notification so that the network adapter can be transitioned to a full-power state.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION MiniportWdiCancelIdleNotification;

void MiniportWdiCancelIdleNotification(
  NDIS_HANDLE MiniportAdapterContext
)
{...}
```

## Parameters

`MiniportAdapterContext`

The handle to the context area that the miniport driver allocated.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>