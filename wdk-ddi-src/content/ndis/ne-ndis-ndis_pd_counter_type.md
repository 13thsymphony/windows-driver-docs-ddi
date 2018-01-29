---
UID : NE:ndis.NDIS_PD_COUNTER_TYPE
title : NDIS_PD_COUNTER_TYPE
author : windows-driver-content
description : The NDIS_PD_COUNTER_TYPE enumeration defines types of PacketDirect Provider Interface (PDPI) counters. Its enumeration values are used in the Type member of the NDIS_PD_COUNTER_PARAMETERS structure.
old-location : netvista\ndis_pd_counter_type.htm
old-project : netvista
ms.assetid : 36DA5A61-2DA4-4CD1-8BA5-74444DC002F0
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PDCounterTypeUnknown, ndis/NDIS_PD_COUNTER_TYPE, ndis/PDCounterTypeTransmitQueue, PDCounterTypeMax, ndis/PDCounterTypeUnknown, netvista.ndis_pd_counter_type, PDCounterTypeTransmitQueue, NDIS_PD_COUNTER_TYPE enumeration [Network Drivers Starting with Windows Vista], ndis/PDCounterTypeReceiveFilter, ndis/PDCounterTypeMax, PDCounterTypeReceiveQueue, NDIS_PD_COUNTER_TYPE, PDCounterTypeReceiveFilter, ndis/PDCounterTypeReceiveQueue
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ndis.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
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
req.typenames : NDIS_PD_COUNTER_TYPE
---

# NDIS_PD_COUNTER_TYPE Enumeration
The <b>NDIS_PD_COUNTER_TYPE</b> enumeration defines types of PacketDirect Provider Interface (PDPI)  counters. Its enumeration values are used in the <b>Type</b> member of the <a href="..\ndis\ns-ndis-_ndis_pd_counter_parameters.md">NDIS_PD_COUNTER_PARAMETERS</a> structure.

## Syntax
````
typedef enum _NDIS_PD_COUNTER_TYPE { 
  PDCounterTypeUnknown,
  PDCounterTypeReceiveQueue,
  PDCounterTypeTransmitQueue,
  PDCounterTypeReceiveFilter,
  PDCounterTypeMax
} NDIS_PD_COUNTER_TYPE;
````

## Constants

<table>

<tr>
<td>PDCounterTypeMax</td>
<td>The maximum value for this enumeration. This value might change in future versions of NDIS header files and binaries.</td>
</tr>

<tr>
<td>PDCounterTypeReceiveFilter</td>
<td>The counter is a receive filter counter.</td>
</tr>

<tr>
<td>PDCounterTypeReceiveQueue</td>
<td>The counter is a receive queue counter.</td>
</tr>

<tr>
<td>PDCounterTypeTransmitQueue</td>
<td>The counter is a transmit queue counter.</td>
</tr>

<tr>
<td>PDCounterTypeUnknown</td>
<td>The counter type is not known.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h |

## See Also

<a href="..\ndis\ns-ndis-_ndis_pd_counter_parameters.md">NDIS_PD_COUNTER_PARAMETERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PD_COUNTER_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>