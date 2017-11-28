---
UID: NS.d3dkmthk._D3DKMT_ADAPTERINFO
title: D3DKMT_ADAPTERINFO
author: windows-driver-content
description: Supplies configuration information about a graphics adapter.
old-location: display\d3dkmt_adapterinfo.htm
old-project: display
ms.assetid: 4b780fb7-f6d4-4248-882c-d0cc96106724
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_ADAPTERINFO, D3DKMT_ADAPTERINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_ADAPTERINFO
req.alt-loc: D3dkmthk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# D3DKMT_ADAPTERINFO structure



## -description
<p>Supplies configuration information about a graphics adapter.</p>


## -syntax

````
typedef struct _D3DKMT_ADAPTERINFO {
  D3DKMT_HANDLE hAdapter;
  LUID          AdapterLuid;
  ULONG         NumOfSources;
  BOOL          bPresentMoveRegionsPreferred;
} D3DKMT_ADAPTERINFO;
````


## -struct-fields
<dl>

### -field <b>hAdapter</b>

<dd>
<p>A handle to the adapter.</p>
</dd>

### -field <b>AdapterLuid</b>

<dd>
<p>A LUID that serves as an identifier for the adapter.</p>
</dd>

### -field <b>NumOfSources</b>

<dd>
<p>The number of video present sources supported by the adapter.</p>
</dd>

### -field <b>bPresentMoveRegionsPreferred</b>

<dd>
<p>If <b>TRUE</b>, the adapter prefers move regions.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>