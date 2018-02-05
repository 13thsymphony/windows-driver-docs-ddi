---
UID : NE:ntddndis._NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE
title : "_NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE"
author : windows-driver-content
description : The NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration identifies the current queue state of a receive queue.
old-location : netvista\ndis_receive_queue_operational_state.htm
old-project : netvista
ms.assetid : a8ae7b19-9dc8-4ccc-b71e-62ec0be1fa99
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddndis/NdisReceiveQueueOperationalStatePaused, ntddndis/PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, NdisReceiveQueueOperationalStateDmaStopped, PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration pointer [Network Drivers Starting with Windows Vista], ntddndis/NdisReceiveQueueOperationalStateMaximum, ntddndis/NdisReceiveQueueOperationalStateUndefined, NdisReceiveQueueOperationalStateMaximum, virtual_machine_queue_ref_db0b16e1-5367-4a29-8a24-474aa09c07f5.xml, ntddndis/NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, NdisReceiveQueueOperationalStateUndefined, NdisReceiveQueueOperationalStatePaused, NdisReceiveQueueOperationalStateRunning, ntddndis/NdisReceiveQueueOperationalStateDmaStopped, _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, netvista.ndis_receive_queue_operational_state, *PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, ntddndis/NdisReceiveQueueOperationalStateRunning
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.20 and later.
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
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, *PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE
---

# _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE Enumeration
The <b>
       NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</b> enumeration identifies the current queue state of a receive
  queue.

## Syntax
````
typedef enum _NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE { 
  NdisReceiveQueueOperationalStateUndefined,
  NdisReceiveQueueOperationalStateRunning,
  NdisReceiveQueueOperationalStatePaused,
  NdisReceiveQueueOperationalStateDmaStopped,
  NdisReceiveQueueOperationalStateMaximum
} NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE, *PNDIS_RECEIVE_QUEUE_OPERATIONAL_STATE;
````

## Constants

<table>

<tr>
<td>NdisReceiveQueueOperationalStateDmaStopped</td>
<td>The DMA operations on the queue are stopped because the queue is being freed, and the queue is in
     the 
     DMA Stopped state. The queue enters the 
     DMA Stopped state when the miniport driver receives an 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-free-queue">
     OID_RECEIVE_FILTER_FREE_QUEUE</a> OID request, stops the DMA operations for the queue, and issues an 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567214">
     NDIS_STATUS_RECEIVE_QUEUE_STATE</a> status indication.</td>
</tr>

<tr>
<td>NdisReceiveQueueOperationalStateMaximum</td>
<td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
</tr>

<tr>
<td>NdisReceiveQueueOperationalStatePaused</td>
<td>The receive queue is in the 
     Paused state. The queue was allocated successfully with the 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-allocate-queue">
     OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a> OID. There are no filters set on the queue.</td>
</tr>

<tr>
<td>NdisReceiveQueueOperationalStateRunning</td>
<td>The receive queue is in the 
     Running state. The queue was allocated successfully, there is at least one filter set on the
     queue, and the miniport driver has completed, or will complete, the 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
     OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a> OID request with a success status.</td>
</tr>

<tr>
<td>NdisReceiveQueueOperationalStateUndefined</td>
<td>The receive queue is in the 
     Undefined state. The queue is not allocated.</td>
</tr>
</table>

## Remarks

The <b>
       NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</b> enumeration is used in the 
    <a href="..\ndis\ns-ndis-_ndis_receive_queue_state.md">NDIS_RECEIVE_QUEUE_STATE</a> and 
    <a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_info.md">
    NDIS_RECEIVE_QUEUE_INFO</a> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_info.md">NDIS_RECEIVE_QUEUE_INFO</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567214">
   NDIS_STATUS_RECEIVE_QUEUE_STATE</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-free-queue">OID_RECEIVE_FILTER_FREE_QUEUE</a>

<a href="..\ndis\ns-ndis-_ndis_receive_queue_state.md">NDIS_RECEIVE_QUEUE_STATE</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
   OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-allocate-queue">
   OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>