---
UID: NS.D3DKMTHK._D3DKMT_GETSHAREDRESOURCEADAPTERLUID
title: _D3DKMT_GETSHAREDRESOURCEADAPTERLUID
author: windows-driver-content
description: Provides information that describes a shared resource and the graphics adapter that the resource was created on.
old-location: display\d3dkmt_getsharedresourceadapterluid.htm
old-project: display
ms.assetid: b7f9413b-3d57-47c4-a8a4-3288cb03af21
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_GETSHAREDRESOURCEADAPTERLUID, D3DKMT_GETSHAREDRESOURCEADAPTERLUID
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
req.alt-api: D3DKMT_GETSHAREDRESOURCEADAPTERLUID
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

# _D3DKMT_GETSHAREDRESOURCEADAPTERLUID structure



## -description
Provides information that describes a shared resource and the graphics adapter that the resource was created on.



## -syntax

````
typedef struct _D3DKMT_GETSHAREDRESOURCEADAPTERLUID {
  D3DKMT_HANDLE hGlobalShare;
  HANDLE        hNtHandle;
  LUID          AdapterLuid;
} D3DKMT_GETSHAREDRESOURCEADAPTERLUID;
````


## -struct-fields

### -field hGlobalShare

[in] A handle to the shared resource.


### -field hNtHandle

[in] An NT handle to the process.


### -field AdapterLuid

[out] A LUID that serves as an identifier for the device that the resource indicated by <b>hGlobalShare</b> was created on. <b>LUID</b> is defined in Dxgi.h.


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