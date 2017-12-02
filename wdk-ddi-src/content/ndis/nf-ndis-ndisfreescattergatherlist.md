---
UID: NF.ndis.NdisFreeScatterGatherList
title: NdisFreeScatterGatherList
author: windows-driver-content
description: The NdisFreeScatterGatherList function frees a scatter/gather list.
old-location: netvista\ndisfreescattergatherlist.htm
old-project: netvista
ms.assetid: 140be989-e578-4bfe-8b9e-56abb274933a
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NdisFreeScatterGatherList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisFreeScatterGatherList
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: = DISPATCH_LEVEL
req.iface: 
---

# NdisFreeScatterGatherList function



## -description
<p>The 
  <b>NdisFreeScatterGatherList</b> function frees a scatter/gather list.</p>


## -syntax

````
VOID NdisFreeScatterGatherList(
  _In_ NDIS_HANDLE          NdisHandle,
  _In_ PSCATTER_GATHER_LIST ScatterGatherListBuffer,
  _In_ BOOLEAN              WriteToDevice
);
````


## -parameters
<dl>

### -param NdisHandle [in]

<dd>
<p>An NDIS driver or instance handle that was obtained during caller initialization. This should be
     the same handle that was passed to the 
     <a href="..\ndis\nf-ndis-ndisbuildscattergatherlist.md">
     NdisBuildScatterGatherList</a> function when the scatter/gather list was created.</p>
</dd>

### -param ScatterGatherListBuffer [in]

<dd>
<p>A pointer to a caller-provided 
     <a href="..\wdm\ns-wdm--scatter-gather-list.md">SCATTER_GATHER_LIST</a> structure to free.
     This must be the same buffer that was passed to the 
     <b>NdisBuildScatterGatherList</b> function when the scatter/gather list was allocated.</p>
</dd>

### -param WriteToDevice [in]

<dd>
<p>A BOOLEAN value that is set to <b>TRUE</b> if the scatter/gather list was used for writing to the device.
     Otherwise, it is <b>FALSE</b>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>NDIS drivers call the 
    <b>NdisFreeScatterGatherList</b> function to free a scatter/gather list that was created with the 
    <a href="..\ndis\nf-ndis-ndisbuildscattergatherlist.md">
    NdisBuildScatterGatherList</a> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.20 and later.</p>
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
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisbuildscattergatherlist.md">NdisBuildScatterGatherList</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--scatter-gather-list.md">SCATTER_GATHER_LIST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeScatterGatherList function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
