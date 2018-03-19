---
UID: NS:ntddndis._NDIS_RECEIVE_QUEUE_FREE_PARAMETERS
title: "_NDIS_RECEIVE_QUEUE_FREE_PARAMETERS"
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_FREE_PARAMETERS structure identifies a receive queue to free.
old-location: netvista\ndis_receive_queue_free_parameters.htm
old-project: netvista
ms.assetid: b67e7929-e6b3-4d0b-aff9-943a7fbae8ee
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_RECEIVE_QUEUE_FREE_PARAMETERS, NDIS_RECEIVE_QUEUE_FREE_PARAMETERS, NDIS_RECEIVE_QUEUE_FREE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_QUEUE_FREE_PARAMETERS, PNDIS_RECEIVE_QUEUE_FREE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_FREE_PARAMETERS, netvista.ndis_receive_queue_free_parameters, ntddndis/NDIS_RECEIVE_QUEUE_FREE_PARAMETERS, ntddndis/PNDIS_RECEIVE_QUEUE_FREE_PARAMETERS, virtual_machine_queue_ref_6084d20e-050b-4e7c-af0e-6ab23269abb0.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
-	Ntddndis.h
api_name:
-	NDIS_RECEIVE_QUEUE_FREE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_QUEUE_FREE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_FREE_PARAMETERS
---

# _NDIS_RECEIVE_QUEUE_FREE_PARAMETERS structure
The <b>NDIS_RECEIVE_QUEUE_FREE_PARAMETERS</b> structure identifies a receive queue to free.

## Syntax
````
typedef struct _NDIS_RECEIVE_QUEUE_FREE_PARAMETERS {
  NDIS_OBJECT_HEADER    Header;
  ULONG                 Flags;
  NDIS_RECEIVE_QUEUE_ID QueueId;
} NDIS_RECEIVE_QUEUE_FREE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_FREE_PARAMETERS;
````

## Members


`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_QUEUE_FREE_PARAMETERS</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to<b> NDIS_RECEIVE_QUEUE_FREE_PARAMETERS_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_FREE_PARAMETERS_REVISION_1</b>.

`Flags`

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

`QueueId`

An <b>NDIS_RECEIVE_QUEUE_ID</b> type value that contains a receive queue identifier. This identifier is an
     integer value between one and the number of queues that the network adapter supports. 

<div class="alert"><b>Note</b>  The default receive queue is always allocated and can never be freed. Drivers must not set the <b>QueueId</b> member to  <b>NDIS_DEFAULT_RECEIVE_QUEUE_ID</b>.</div>
<div> </div>

## Remarks
The <b>NDIS_RECEIVE_QUEUE_FREE_PARAMETERS</b> structure is used in the 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-free-queue">
    OID_RECEIVE_FILTER_FREE_QUEUE</a> OID.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-free-queue">OID_RECEIVE_FILTER_FREE_QUEUE</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>