---
UID : NC:ndis.NET_BUFFER_FREE_MDL_HANDLER
title : NET_BUFFER_FREE_MDL_HANDLER
author : windows-driver-content
description : The NetFreeMdl function frees an MDL that was previously allocated by the NetAllocateMdl function.
old-location : netvista\netfreemdl.htm
old-project : netvista
ms.assetid : a92b2de9-231d-4dcc-8220-857063a35eb1
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.netfreemdl, NetFreeMdl callback function [Network Drivers Starting with Windows Vista], NetFreeMdl, NET_BUFFER_FREE_MDL_HANDLER, NET_BUFFER_FREE_MDL_HANDLER, ndis/NetFreeMdl, ndis_netbuf_functions_ref_a005ffba-5557-4d9b-a647-63e9e06fa8ef.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
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
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# NET_BUFFER_FREE_MDL_HANDLER callback function
The 
  <i>NetFreeMdl</i> function frees an MDL that was previously allocated by the 
  <a href="..\ndis\nc-ndis-net_buffer_allocate_mdl_handler.md">NetAllocateMdl</a> function.

## Syntax

```
NET_BUFFER_FREE_MDL_HANDLER NetBufferFreeMdlHandler;

void NetBufferFreeMdlHandler(
  PMDL Mdl
)
{...}
```

## Parameters

`Mdl`

A pointer to the MDL that is to be freed.


## Return Value

None

## Remarks

If the NDIS driver specifies an entry point for the 
    <i>NetFreeMdl</i> function at the 
    <i>FreeMdl</i> parameter of the 
    <mshelp:link keywords="netvista.ndisadvancenetbufferdatastart" tabindex="0"><b>
    NdisAdvanceNetBufferDataStart</b></mshelp:link> function, NDIS calls 
    <i>NetFreeMdl</i> to free an MDL and memory.

<i>NetFreeMdl</i> frees the MDL and memory that were allocated by the 
    <a href="..\ndis\nc-ndis-net_buffer_allocate_mdl_handler.md">NetAllocateMdl</a> function.

When 
    <i>NetFreeMdl</i> frees the memory, it should use the same memory management mechanism that was used in 
    <i>NetAllocateMdl</i> to allocate the memory.

NDIS calls 
    <i>NetFreeMdl</i> at IRQL &lt;= DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ndis\nc-ndis-net_buffer_allocate_mdl_handler.md">NetAllocateMdl</a>

<mshelp:link keywords="netvista.ndisadvancenetbufferdatastart" tabindex="0"><b>
   NdisAdvanceNetBufferDataStart</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_BUFFER_FREE_MDL_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>