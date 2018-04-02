---
UID: NS:ndis._NDIS_PD_FILTER_COUNTER
title: "_NDIS_PD_FILTER_COUNTER"
author: windows-driver-content
description: This structure is used to hold counter information for a filter.
old-location: netvista\ndis_pd_filter_counter.htm
old-project: netvista
ms.assetid: 74660B47-0219-4724-AD7E-B20A2BB520EB
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_PD_FILTER_COUNTER, NDIS_PD_FILTER_COUNTER structure [Network Drivers Starting with Windows Vista], PNDIS_PD_FILTER_COUNTER, PNDIS_PD_FILTER_COUNTER structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PD_FILTER_COUNTER, ndis/NDIS_PD_FILTER_COUNTER, ndis/PNDIS_PD_FILTER_COUNTER, netvista.ndis_pd_filter_counter
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
-	NDIS_PD_FILTER_COUNTER
product:
- Windows
targetos: Windows
req.typenames: NDIS_PD_FILTER_COUNTER
---

# _NDIS_PD_FILTER_COUNTER structure
This structure is used to hold counter information for a filter.

## Syntax
```
typedef struct _NDIS_PD_FILTER_COUNTER {
  ULONG64 PacketsMatched;
  ULONG64 BytesMatched;
} NDIS_PD_FILTER_COUNTER;
```

## Members


`PacketsMatched`

The amount of packets that match.

`BytesMatched`

The amount of bytes that match.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | ndis.h |