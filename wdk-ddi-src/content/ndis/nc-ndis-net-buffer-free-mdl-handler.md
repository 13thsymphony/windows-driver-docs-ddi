---
UID: NC.ndis.NET_BUFFER_FREE_MDL_HANDLER
title: NET_BUFFER_FREE_MDL_HANDLER
author: windows-driver-content
description: The NetFreeMdl function frees an MDL that was previously allocated by the NetAllocateMdl function.
old-location: netvista\netfreemdl.htm
old-project: netvista
ms.assetid: a92b2de9-231d-4dcc-8220-857063a35eb1
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NetFreeMdl
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# NET_BUFFER_FREE_MDL_HANDLER callback



## -description
<p>The 
  <i>NetFreeMdl</i> function frees an MDL that was previously allocated by the 
  <a href="..\ndis\nc-ndis-net-buffer-allocate-mdl-handler.md">NetAllocateMdl</a> function.</p>


## -prototype

````
NET_BUFFER_FREE_MDL_HANDLER NetFreeMdl;

VOID NetFreeMdl(
  _In_ PMDL Mdl
)
{ ... }
````


## -parameters
<dl>

### -param <i>Mdl</i> [in]

<dd>
<p>A pointer to the MDL that is to be freed.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If the NDIS driver specifies an entry point for the 
    <i>NetFreeMdl</i> function at the 
    <i>FreeMdl</i> parameter of the 
    <a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
    NdisAdvanceNetBufferDataStart</a> function, NDIS calls 
    <i>NetFreeMdl</i> to free an MDL and memory.</p>

<p><i>NetFreeMdl</i> frees the MDL and memory that were allocated by the 
    <a href="..\ndis\nc-ndis-net-buffer-allocate-mdl-handler.md">NetAllocateMdl</a> function.</p>

<p>When 
    <i>NetFreeMdl</i> frees the memory, it should use the same memory management mechanism that was used in 
    <i>NetAllocateMdl</i> to allocate the memory.</p>

<p>NDIS calls 
    <i>NetFreeMdl</i> at IRQL &lt;= DISPATCH_LEVEL.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-net-buffer-allocate-mdl-handler.md">NetAllocateMdl</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
   NdisAdvanceNetBufferDataStart</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_BUFFER_FREE_MDL_HANDLER callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
