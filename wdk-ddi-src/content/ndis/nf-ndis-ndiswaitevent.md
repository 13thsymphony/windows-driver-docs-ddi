---
UID : NF:ndis.NdisWaitEvent
title : NdisWaitEvent function
author : windows-driver-content
description : The NdisWaitEvent function puts the caller into a wait state until the given event is set to the Signaled state or the wait times out.
old-location : netvista\ndiswaitevent.htm
old-project : netvista
ms.assetid : fefdb56f-6689-4a4f-a198-6108190624f0
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : NdisWaitEvent
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWaitEvent (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisWaitEvent (NDIS 5.1)) in Windows   XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NdisWaitEvent
req.alt-loc : ndis.lib,ndis.dll
req.ddi-compliance : Irql_Miscellaneous_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisWaitEvent function
The
  <b>NdisWaitEvent</b> function puts the caller into a wait state until the given event is set to the Signaled
  state or the wait times out.

## Syntax

````
BOOLEAN NdisWaitEvent(
  _In_ PNDIS_EVENT Event,
  _In_ UINT        MsToWait
);
````

## Parameters

`Event`

A pointer to an initialized event object for which the caller provides the storage.

`MsToWait`

The number of milliseconds the caller will wait if the event is not set to the 
     <i>signaled</i> state within that interval. A value of zero specifies that the caller will wait for the
     event indefinitely.


## Return Value

<b>NdisWaitEvent</b> returns <b>TRUE</b> if the event is in the 
     <i>signaled</i> state when the wait is satisfied.

## Remarks

<b>NdisWaitEvent</b> returns control to its caller when the given event is signaled or the specified 
    <i>MsToWait</i> interval expires, whichever is sooner. If the event is currently in the 
    <i>signaled</i> state when this call occurs, 
    <b>NdisWaitEvent</b> returns control immediately.

A miniport driver typically calls 
    <b>NdisWaitEvent</b> from its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> and 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> functions. A protocol
    driver typically calls 
    <b>NdisWaitEvent</b> from its 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> and 
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
    ProtocolUnbindAdapterEx</a> functions.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisinitializeevent.md">NdisInitializeEvent</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisresetevent.md">NdisResetEvent</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndissetevent.md">NdisSetEvent</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisWaitEvent function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>