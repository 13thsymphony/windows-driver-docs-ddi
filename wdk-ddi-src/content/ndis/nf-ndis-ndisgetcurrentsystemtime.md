---
UID : NF:ndis.NdisGetCurrentSystemTime
title : NdisGetCurrentSystemTime macro
author : windows-driver-content
description : The NdisGetCurrentSystemTime function returns the current system time, suitable for setting timestamps.
old-location : netvista\ndisgetcurrentsystemtime.htm
old-project : netvista
ms.assetid : eef32784-ea27-42c0-9a7a-74ce3d76665d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisGetCurrentSystemTime macro [Network Drivers Starting with Windows Vista], ndis_sysinfo_ref_cfd2358c-a52a-43d9-a07b-c64abb3e28b1.xml, NdisGetCurrentSystemTime, netvista.ndisgetcurrentsystemtime, ndis/NdisGetCurrentSystemTime
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetCurrentSystemTime (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetCurrentSystemTime (NDIS   5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisGetCurrentSystemTime function
The 
  <b>NdisGetCurrentSystemTime</b> function returns the current system time, suitable for setting
  timestamps.

## Syntax

````
VOID NdisGetCurrentSystemTime(
  [in] PLARGE_INTEGER pSystemTime
);
````

## Parameters

`_pSystemTime`

TBD


## Return Value

None

## Remarks

An NDIS driver might also call 
    <b>NdisGetCurrentSystemTime</b> if it maintains a count of how many packets it receives within any
    particular interval to tune its performance dynamically. For example, a miniport driver could call 
    <b>NdisGetCurrentSystemTime</b> for each receive interrupt to determine periods of high network traffic,
    when the driver might disable one or more types of interrupts on the NIC and enable a polling 
    <a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a> function to process
    receive indications or send requests.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetCurrentSystemTime macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>