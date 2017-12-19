---
UID: NE.ntddndis._NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE
title: _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration identifies the current queue state of a receive queue.
old-location: netvista\ndis_receive_queue_operational_state.htm
old-project: NetVista
ms.assetid: a8ae7b19-9dc8-4ccc-b71e-62ec0be1fa99
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, *PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE
req.alt-loc: Ntddndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration



## -description
The <b>
       NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</b> enumeration identifies the current queue state of a receive
  queue.



## -syntax

````
typedef enum _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE { 
  NdisReceiveQueueOperationalStateUndefined,
  NdisReceiveQueueOperationalStateRunning,
  NdisReceiveQueueOperationalStatePaused,
  NdisReceiveQueueOperationalStateDmaStopped,
  NdisReceiveQueueOperationalStateMaximum
} NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, *PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE;
````


## -enum-fields

### -field NdisReceiveQueueOperationalStateUndefined

The receive queue is in the 
     Undefined state. The queue is not allocated.


### -field NdisReceiveQueueOperationalStateRunning

The receive queue is in the 
     Running state. The queue was allocated successfully, there is at least one filter set on the
     queue, and the miniport driver has completed, or will complete, the 
     <a href="netvista.oid_receive_filter_queue_allocation_complete">
     OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a> OID request with a success status.


### -field NdisReceiveQueueOperationalStatePaused

The receive queue is in the 
     Paused state. The queue was allocated successfully with the 
     <a href="netvista.oid_receive_filter_allocate_queue">
     OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a> OID. There are no filters set on the queue.


### -field NdisReceiveQueueOperationalStateDmaStopped

The DMA operations on the queue are stopped because the queue is being freed, and the queue is in
     the 
     DMA Stopped state. The queue enters the 
     DMA Stopped state when the miniport driver receives an 
     <a href="netvista.oid_receive_filter_free_queue">
     OID_RECEIVE_FILTER_FREE_QUEUE</a> OID request, stops the DMA operations for the queue, and issues an 
     <a href="netvista.ndis_status_receive_queue_state">
     NDIS_STATUS_RECEIVE_QUEUE_STATE</a> status indication.


### -field NdisReceiveQueueOperationalStateMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks
The <b>
       NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</b> enumeration is used in the 
    <a href="netvista.ndis_receive_queue_state">NDIS_RECEIVE_QUEUE_STATE</a> and 
    <a href="netvista.ndis_receive_queue_info">
    NDIS_RECEIVE_QUEUE_INFO</a> structures.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.20 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_receive_queue_info">NDIS_RECEIVE_QUEUE_INFO</a>
</dt>
<dt>
<a href="netvista.ndis_receive_queue_state">NDIS_RECEIVE_QUEUE_STATE</a>
</dt>
<dt>
<a href="netvista.ndis_status_receive_queue_state">
   NDIS_STATUS_RECEIVE_QUEUE_STATE</a>
</dt>
<dt>
<a href="netvista.oid_receive_filter_allocate_queue">
   OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569789">OID_RECEIVE_FILTER_FREE_QUEUE</a>
</dt>
<dt>
<a href="netvista.oid_receive_filter_queue_allocation_complete">
   OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

