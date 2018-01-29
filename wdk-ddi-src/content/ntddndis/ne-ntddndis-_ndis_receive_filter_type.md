---
UID : NE:ntddndis._NDIS_RECEIVE_FILTER_TYPE
title : _NDIS_RECEIVE_FILTER_TYPE
author : windows-driver-content
description : The NDIS_RECEIVE_FILTER_TYPE enumeration identifies the receive filter types that the miniport driver supports.
old-location : netvista\ndis_receive_filter_type.htm
old-project : netvista
ms.assetid : 2810be51-4b38-4462-9c16-67a9f28da5c9
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*PNDIS_RECEIVE_FILTER_TYPE, ntddndis/NDIS_RECEIVE_FILTER_TYPE, ntddndis/NdisReceiveFilterTypeVMQueue, NDIS_RECEIVE_FILTER_TYPE, PNDIS_RECEIVE_FILTER_TYPE, NdisReceiveFilterTypeMaximum, PNDIS_RECEIVE_FILTER_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], NdisReceiveFilterTypePacketCoalescing, virtual_machine_queue_ref_8965d6c0-b700-46cd-9386-0e2cdc5da4c9.xml, ntddndis/PNDIS_RECEIVE_FILTER_TYPE, NDIS_RECEIVE_FILTER_TYPE enumeration [Network Drivers Starting with Windows Vista], netvista.ndis_receive_filter_type, NdisReceiveFilterTypeUndefined, ntddndis/NdisReceiveFilterTypePacketCoalescing, ntddndis/NdisReceiveFilterTypeMaximum, _NDIS_RECEIVE_FILTER_TYPE, ntddndis/NdisReceiveFilterTypeUndefined, NdisReceiveFilterTypeVMQueue"
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
req.typenames : NDIS_RECEIVE_FILTER_TYPE, *PNDIS_RECEIVE_FILTER_TYPE
---

# _NDIS_RECEIVE_FILTER_TYPE Enumeration
The <b>NDIS_RECEIVE_FILTER_TYPE</b> enumeration identifies the receive filter types that the miniport driver
  supports.

## Syntax
````
typedef enum _NDIS_RECEIVE_FILTER_TYPE { 
  NdisReceiveFilterTypeUndefined,
  NdisReceiveFilterTypeVMQueue,
  NdisReceiveFilterTypePacketCoalescing,
  NdisReceiveFilterTypeMaximum
} NDIS_RECEIVE_FILTER_TYPE, *PNDIS_RECEIVE_FILTER_TYPE;
````

## Constants

<table>

<tr>
<td>NdisReceiveFilterTypeMaximum</td>
<td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
</tr>

<tr>
<td>NdisReceiveFilterTypePacketCoalescing</td>
<td>A packet coalescing filter.</td>
</tr>

<tr>
<td>NdisReceiveFilterTypeUndefined</td>
<td>An undefined filter.</td>
</tr>

<tr>
<td>NdisReceiveFilterTypeVMQueue</td>
<td>A filter for a virtual machine (VM) receive queue. This receive queue has been allocated by the miniport driver that supports the virtual machine queue (VMQ) or single root I/O virtualization (SR-IOV) interface.</td>
</tr>
</table>

## Remarks

The NDIS_RECEIVE_FILTER_TYPE enumeration is used in the 
    <mshelp:link keywords="netvista.ndis_receive_filter_parameters" tabindex="0"><b>
    NDIS_RECEIVE_FILTER_PARAMETERS</b></mshelp:link> structure.

For more information about VMQ, see <a href="https://msdn.microsoft.com/c502c7d6-bdf1-4656-b5a5-339250910f08">Virtual Machine Queue (VMQ)</a>.

For more information about SR-IOV, see <a href="https://msdn.microsoft.com/E64DD4F0-D5F8-4FFF-931B-C04C5C42D000">Single Root I/O Virtualization (SR-IOV)</a>.

For more information about packet coalescing, see <a href="https://msdn.microsoft.com/500FBF0F-54D9-4675-8E2D-447387DA8798">NDIS Packet Coalescing</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<mshelp:link keywords="netvista.ndis_receive_filter_parameters" tabindex="0"><b>
   NDIS_RECEIVE_FILTER_PARAMETERS</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_FILTER_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>