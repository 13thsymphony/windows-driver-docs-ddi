---
UID: NS.D3DKMTHK._D3DKMT_ADAPTERINFO
title: _D3DKMT_ADAPTERINFO
author: windows-driver-content
description: Supplies configuration information about a graphics adapter.
old-location: display\d3dkmt_adapterinfo.htm
old-project: display
ms.assetid: 4b780fb7-f6d4-4248-882c-d0cc96106724
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_ADAPTERINFO, D3DKMT_ADAPTERINFO
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
---

# _D3DKMT_ADAPTERINFO structure



## -description
Supplies configuration information about a graphics adapter.



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

### -field hAdapter

A handle to the adapter.


### -field AdapterLuid

A LUID that serves as an identifier for the adapter.


### -field NumOfSources

The number of video present sources supported by the adapter.


### -field bPresentMoveRegionsPreferred

If <b>TRUE</b>, the adapter prefers move regions.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>