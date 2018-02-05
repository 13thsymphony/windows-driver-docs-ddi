---
UID : NF:ndis.NdisStallExecution
title : NdisStallExecution macro
author : windows-driver-content
description : The NdisStallExecution function stalls the caller on the current processor for a given interval.
old-location : netvista\ndisstallexecution.htm
old-project : netvista
ms.assetid : 590f5a1a-fd78-408e-b4f0-555f08694c43
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/NdisStallExecution, ndis_delay_ref_de9bdd45-0bed-44cc-bdce-3ecd81842010.xml, NdisStallExecution, netvista.ndisstallexecution, NdisStallExecution macro [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisStallExecution (NDIS 5.1))   in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisStallExecution (NDIS 5.1))   in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : NdisStallExecution_Delay
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : ndis.h
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisStallExecution function
The 
  <b>NdisStallExecution</b> function stalls the caller on the current processor for a given interval.

## Syntax

````
VOID NdisStallExecution(
  [in] UINT MicrosecondsToStall
);
````

## Parameters

`MicroSecondsToStall`

TBD


## Return Value

None

## Remarks

<b>NdisStallExecution</b> is a processor-dependent function that busy-waits for at least the specified
    number of microseconds, but not significantly longer.

This function should be called by drivers that must wait for an interval of more than a few
    instructions but less than 50 microseconds. Drivers that call this routine should minimize the number of
    microseconds that they specify.

If a driver must wait for an interval longer than 50 microseconds, it should call the 
    <a href="..\ndis\nf-ndis-ndismsleep.md">NdisMSleep</a> function. Note that callers of 
    <b>NdisMSleep</b> run at IRQL &lt; DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisStallExecution (NDIS 5.1))   in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisStallExecution (NDIS 5.1))   in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisStallExecution (NDIS 5.1))   in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisStallExecution (NDIS 5.1))   in Windows XP. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | ndis.h |
| **IRQL** | Any level |
| **DDI compliance rules** | NdisStallExecution_Delay |

## See Also

<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndismsleep.md">NdisMSleep</a>

<a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisStallExecution macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>