---
UID: NF:ndis.NdisInterlockedAddLargeStatistic
title: NdisInterlockedAddLargeStatistic macro
author: windows-driver-content
description: The NdisInterlockedAddLargeStatistic function performs an interlocked addition of a ULONG increment value to a LARGE_INTEGER addend value.
old-location: netvista\ndisinterlockedaddlargestatistic.htm
old-project: netvista
ms.assetid: 7bc753b1-5e09-431b-b226-fb7194dd6947
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisInterlockedAddLargeStatistic, NdisInterlockedAddLargeStatistic macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedAddLargeStatistic, ndis_interlocked_ref_f1b7622e-acc8-45d7-b85e-c39058b595fe.xml, netvista.ndisinterlockedaddlargestatistic
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisInterlockedAddLargeStatistic (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisInterlockedAddLargeStatistic (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisInterlockedAddLargeStatistic
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisInterlockedAddLargeStatistic function
The 
  <b>NdisInterlockedAddLargeStatistic</b> function performs an interlocked addition of a ULONG increment value
  to a LARGE_INTEGER addend value.

## Syntax

````
VOID NdisInterlockedAddLargeStatistic(
  [in] PLARGE_INTEGER Addend,
  [in] ULONG          Increment
);
````

## Parameters

`_Addend`

A pointer to a LARGE_INTEGER value that is incremented by the value of 
     <i>Increment</i> .

`_Increment`

A ULONG value that is added to the value to which the 
     <i>Addend</i> parameter points.


## Return Value

None

## Remarks

Functions that perform interlocked operations must not cause a page fault to occur. Neither their code
    nor any of the data that they access can cause a page fault without bringing down the local computer.

<b>NdisInterlockedAddLargeStatistic</b> masks interrupts and can be safely used to synchronize a driver's 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function with other
    driver code.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisInterlockedAddLargeStatistic (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisInterlockedAddLargeStatistic (NDIS 5.1)) in Windows XP.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInterlockedAddLargeStatistic macro%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>