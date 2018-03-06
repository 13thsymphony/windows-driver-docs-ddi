---
UID: NS:ndis._NDIS_PD_COUNTER_VALUE
title: "_NDIS_PD_COUNTER_VALUE"
author: windows-driver-content
description: This structure is used to hold a counter value for a queue or filter counter.
old-location: netvista\ndis_pd_counter_value.htm
old-project: netvista
ms.assetid: 0C2424C5-F6EE-4D07-B5C3-CEC3520AFFDC
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PNDIS_PD_COUNTER_VALUE, NDIS_PD_COUNTER_VALUE, NDIS_PD_COUNTER_VALUE union [Network Drivers Starting with Windows Vista], PNDIS_PD_COUNTER_VALUE, PNDIS_PD_COUNTER_VALUE union pointer [Network Drivers Starting with Windows Vista], _NDIS_PD_COUNTER_VALUE, ndis/NDIS_PD_COUNTER_VALUE, ndis/PNDIS_PD_COUNTER_VALUE, netvista.ndis_pd_counter_value"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	NDIS_PD_COUNTER_VALUE
product: Windows
targetos: Windows
req.typenames: NDIS_PD_COUNTER_VALUE, *PNDIS_PD_COUNTER_VALUE
---

# _NDIS_PD_COUNTER_VALUE structure
This structure is used to hold a counter value for a queue or filter counter.

## Syntax
````
typedef union _NDIS_PD_COUNTER_VALUE {
  NDIS_PD_RECEIVE_QUEUE_COUNTER  ReceiveQueue;
  NDIS_PD_TRANSMIT_QUEUE_COUNTER TransmitQueue;
  NDIS_PD_FILTER_COUNTER         Filter;
} NDIS_PD_COUNTER_VALUE, *PNDIS_PD_COUNTER_VALUE;
````

## Members


`Filter`

See <a href="..\ndis\ns-ndis-_ndis_pd_filter_counter.md">NDIS_PD_FILTER_COUNTER</a>.

`ReceiveQueue`

See <a href="..\ndis\ns-ndis-_ndis_pd_receive_queue_counter.md">NDIS_PD_RECEIVE_QUEUE_COUNTER</a>.

`TransmitQueue`

See <a href="..\ndis\ns-ndis-_ndis_pd_transmit_queue_counter.md">NDIS_PD_TRANSMIT_QUEUE_COUNTER</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | ndis.h |