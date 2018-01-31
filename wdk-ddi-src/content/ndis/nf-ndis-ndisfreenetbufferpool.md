---
UID : NF:ndis.NdisFreeNetBufferPool
title : NdisFreeNetBufferPool function
author : windows-driver-content
description : Call the NdisFreeNetBufferPool function to free NET_BUFFER structure pools that are created with the NdisAllocateNetBufferPool function.
old-location : netvista\ndisfreenetbufferpool.htm
old-project : netvista
ms.assetid : e1ea63d1-9322-44c7-8196-2fe1a7b6a220
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis_netbuf_functions_ref_8fcb5f46-efc3-4059-9774-cbdf14c5500a.xml, NdisFreeNetBufferPool, NdisFreeNetBufferPool function [Network Drivers Starting with Windows Vista], netvista.ndisfreenetbufferpool, ndis/NdisFreeNetBufferPool
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_NetBuffer_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFreeNetBufferPool function
Call the 
  <b>NdisFreeNetBufferPool</b> function to free 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure pools that are created with
  the 
  <mshelp:link keywords="netvista.ndisallocatenetbufferpool" tabindex="0"><b>
  NdisAllocateNetBufferPool</b></mshelp:link> function.

## Syntax

````
VOID NdisFreeNetBufferPool(
  _In_ NDIS_HANDLE PoolHandle
);
````

## Parameters

`PoolHandle`

The pool handle for the NET_BUFFER structure pool to be freed.


## Return Value

None

## Remarks

You should free all the 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures in a pool before freeing
    the NET_BUFFER structure pool. Call the 
    <a href="..\ndis\nf-ndis-ndisfreenetbuffer.md">NdisFreeNetBuffer</a> function to free each
    NET_BUFFER structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_NetBuffer_Function |

## See Also

<a href="..\ndis\nf-ndis-ndisfreenetbuffer.md">NdisFreeNetBuffer</a>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<a href="..\ndis\nf-ndis-ndisallocatenetbufferpool.md">NdisAllocateNetBufferPool</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeNetBufferPool function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>