---
UID: NS.d3dkmthk._D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
title: D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
author: windows-driver-content
description: Describes information that is required to map an NT process handle to a graphics processing unit (GPU) synchronization object.
old-location: display\d3dkmt_opensyncobjectfromnthandle.htm
old-project: display
ms.assetid: 163ce4ed-e81b-4b69-b1a7-4ea2b9e8f437
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_OPENSYNCOBJECTFROMNTHANDLE, D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
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
req.alt-api: D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
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

# D3DKMT_OPENSYNCOBJECTFROMNTHANDLE structure



## -description
<p>Describes information that is required to map an NT process handle to a graphics processing unit (GPU) synchronization object.</p>


## -syntax

````
typedef struct _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE {
  HANDLE        hNtHandle;
  D3DKMT_HANDLE hSyncObject;
} D3DKMT_OPENSYNCOBJECTFROMNTHANDLE;
````


## -struct-fields
<dl>

### -field <b>hNtHandle</b>

<dd>
<p>[in] An NT handle to the process.</p>
</dd>

### -field <b>hSyncObject</b>

<dd>
<p>[out] A handle of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode handle to the kernel-mode synchronization object.</p>
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