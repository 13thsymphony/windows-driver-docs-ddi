---
UID : NF:ndis.NdisAdjustNetBufferCurrentMdl
title : NdisAdjustNetBufferCurrentMdl function
author : windows-driver-content
description : The NdisAdjustNetBufferCurrentMdl function updates a NET_BUFFER structure based on the current data offset.
old-location : netvista\ndisadjustnetbuffercurrentmdl.htm
old-project : netvista
ms.assetid : 5d05793b-cb35-435d-aa59-6ac380668d91
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : NdisAdjustNetBufferCurrentMdl
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
req.alt-api : NdisAdjustNetBufferCurrentMdl
req.alt-loc : ndis.lib,ndis.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : Any level (see Remarks section)
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisAdjustNetBufferCurrentMdl function
The 
  <b>NdisAdjustNetBufferCurrentMdl</b> function updates a 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure based on the current data
  offset.

## Syntax

````
VOID NdisAdjustNetBufferCurrentMdl(
  _In_ PNET_BUFFER NetBuffer
);
````

## Parameters

`NetBuffer`

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure.


## Return Value

None

## Remarks

The 
    <b>NdisAdjustNetBufferCurrentMdl</b> function recalculates and sets the 
    <b>CurrentMdl</b> and 
    <b>CurrentMdlOffset</b> members of a 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure based on the 
    <b>DataOffset</b> member of the NET_BUFFER structure.

Callers of 
    <b>NdisAdjustNetBufferCurrentMdl</b> can run at any IRQL, but typically run at IRQL &lt;=
    DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | Any level (see Remarks section) |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAdjustNetBufferCurrentMdl function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>