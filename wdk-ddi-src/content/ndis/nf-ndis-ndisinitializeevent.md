---
UID: NF:ndis.NdisInitializeEvent
title: NdisInitializeEvent function
author: windows-driver-content
description: The NdisInitializeEvent function sets up an event object during driver initialization to be used subsequently as a synchronization mechanism.
old-location: netvista\ndisinitializeevent.htm
old-project: netvista
ms.assetid: 7f7eac7e-f512-4446-a83b-92d313c14420
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisInitializeEvent function [Network Drivers Starting with Windows Vista], ndis/NdisInitializeEvent, netvista.ndisinitializeevent, ndis_event_ref_35523d4a-3084-43ea-9dc0-6e9017b9ed22.xml, NdisInitializeEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInitializeEvent (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInitializeEvent (NDIS   5.1)) in Windows XP.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisInitializeEvent
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisInitializeEvent function
The 
  <b>NdisInitializeEvent</b> function sets up an event object during driver initialization to be used
  subsequently as a synchronization mechanism.

## Syntax

````
VOID NdisInitializeEvent(
  _Out_ PNDIS_EVENT Event
);
````

## Parameters

`Event`

A pointer to caller-supplied storage for the event object, which is opaque to drivers.


## Return Value

None

## Remarks

The 
    <b>NdisInitializeEvent</b> function creates an event object that has an event type of 
    <b>NotificationEvent</b> and an initial state of 
    <i>not-signaled</i>. For more information about notification events, see 
    <a href="https://msdn.microsoft.com/4b7807f0-bbea-4402-b028-9ac73724717f">Defining and Using an Event
    Object</a>.

The 
    <i>Event</i> pointer passed to 
    <b>NdisInitializeEvent</b> is a required parameter to all other 
    <b>Ndis<i>Xxx</i>Event</b> functions.

While driver functions that must run at IRQL &lt;= DISPATCH_LEVEL can call the 
    <a href="..\ndis\nf-ndis-ndissetevent.md">NdisSetEvent</a> and 
    <a href="..\ndis\nf-ndis-ndisresetevent.md">NdisResetEvent</a> functions ,calling 
    <b>NdisWaitEvent</b> from any IRQL &gt; PASSIVE_LEVEL is a fatal error.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInitializeEvent (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInitializeEvent (NDIS   5.1)) in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInitializeEvent (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInitializeEvent (NDIS   5.1)) in Windows XP. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndisresetevent.md">NdisResetEvent</a>



<a href="..\ndis\nf-ndis-ndissetevent.md">NdisSetEvent</a>



<a href="..\ndis\nf-ndis-ndiswaitevent.md">NdisWaitEvent</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInitializeEvent function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>