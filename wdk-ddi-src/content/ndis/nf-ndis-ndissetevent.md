---
UID: NF:ndis.NdisSetEvent
title: NdisSetEvent function
author: windows-driver-content
description: The NdisSetEvent function sets a given event to the signaled state if it was not already Signaled.
old-location: netvista\ndissetevent.htm
old-project: netvista
ms.assetid: 3f45b8d0-2d5b-4601-a307-48257cdcb4ba
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisSetEvent, NdisSetEvent function [Network Drivers Starting with Windows Vista], ndis/NdisSetEvent, ndis_event_ref_3abf6ebc-6dcf-4b3e-8e39-2902b9b00adf.xml, netvista.ndissetevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisSetEvent (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisSetEvent (NDIS 5.1)) in Windows   XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Synch_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisSetEvent
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisSetEvent function
The 
  <b>NdisSetEvent</b> function sets a given event to the signaled state if it was not already Signaled.

## Syntax

````
VOID NdisSetEvent(
  _In_ PNDIS_EVENT Event
);
````

## Parameters

`Event`

A pointer to an initialized event object for which the caller provides the storage.


## Return Value

None

## Remarks

When an event attains the 
    <i>signaled</i> state, it causes waits on the event to be satisfied and any waiters to be dispatched for
    execution.

After a call to 
    <b>NdisSetEvent</b>, the event remains in the 
    <i>signaled</i> state until the driver calls the 
    <a href="..\ndis\nf-ndis-ndisresetevent.md">NdisResetEvent</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisSetEvent (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisSetEvent (NDIS 5.1)) in Windows   XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Synch_Function |

## See Also

<a href="..\ndis\nf-ndis-ndisresetevent.md">NdisResetEvent</a>



<a href="..\ndis\nf-ndis-ndisinitializeevent.md">NdisInitializeEvent</a>



<a href="..\ndis\nf-ndis-ndiswaitevent.md">NdisWaitEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisSetEvent function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>