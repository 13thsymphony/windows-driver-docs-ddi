---
UID: NS:ntddndis._OFFLOAD_IPSEC_DELETE_UDPESP_SA
title: "_OFFLOAD_IPSEC_DELETE_UDPESP_SA"
author: windows-driver-content
description: The OFFLOAD_IPSEC_DELETE_UDPESP_SA structure contains information for each security association (SA) and parser entry that a miniport driver deletes from a NIC.
old-location: netvista\offload_ipsec_delete_udpesp_sa.htm
old-project: netvista
ms.assetid: f1304fb4-87c8-4a0f-a10f-6a2c5cbaed20
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*POFFLOAD_IPSEC_DELETE_UDPESP_SA, 216offload_7d48a18d-546e-4e72-baf6-5a9e8de5a615.xml, OFFLOAD_IPSEC_DELETE_UDPESP_SA, OFFLOAD_IPSEC_DELETE_UDPESP_SA structure [Network Drivers Starting with Windows Vista], POFFLOAD_IPSEC_DELETE_UDPESP_SA, POFFLOAD_IPSEC_DELETE_UDPESP_SA structure pointer [Network Drivers Starting with Windows Vista], _OFFLOAD_IPSEC_DELETE_UDPESP_SA, netvista.offload_ipsec_delete_udpesp_sa, ntddndis/OFFLOAD_IPSEC_DELETE_UDPESP_SA, ntddndis/POFFLOAD_IPSEC_DELETE_UDPESP_SA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	OFFLOAD_IPSEC_DELETE_UDPESP_SA
product: Windows
targetos: Windows
req.typenames: OFFLOAD_IPSEC_DELETE_UDPESP_SA, *POFFLOAD_IPSEC_DELETE_UDPESP_SA
---

# _OFFLOAD_IPSEC_DELETE_UDPESP_SA structure
The OFFLOAD_IPSEC_DELETE_UDPESP_SA structure contains information for each security association (SA)
  and parser entry that a miniport driver deletes from a NIC.

## Syntax
````
typedef struct _OFFLOAD_IPSEC_DELETE_UDPESP_SA {
  HANDLE OffloadHandle;
  HANDLE EncapTypeEntryOffldHandle;
} OFFLOAD_IPSEC_DELETE_UDPESP_SA, *POFFLOAD_IPSEC_DELETE_UDPESP_SA;
````

## Members


`OffloadHandle`

The handle for the SA to be deleted.

`EncapTypeEntryOffldHandle`

When <b>NULL</b>, the miniport does not have to delete a parser entry in addition to the specified SA.
     When non-<b>NULL</b>, this member specifies the handle for the parser entry to be deleted.

## Remarks
The OFFLOAD_IPSEC_DELETE_UDPESP_SA structure is used with the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff569809">
    OID_TCP_TASK_IPSEC_DELETE_UDPESP_SA</a> OID.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff569809">
   OID_TCP_TASK_IPSEC_DELETE_UDPESP_SA</a>