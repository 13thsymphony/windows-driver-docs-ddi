---
UID: NS.D3D12UMDDI.D3D12DDIARG_OPEN_CRYPTO_SESSION_0030
title: D3D12DDIARG_OPEN_CRYPTO_SESSION_0030
author: windows-driver-content
description: Opens a crypto session.
old-location: display\d3d12ddiarg-open-crypto-session-0030.htm
old-project: display
ms.assetid: 8b500956-6d22-4862-b9e4-e3cb545fcc0e
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D12DDIARG_OPEN_CRYPTO_SESSION_0030, D3D12DDIARG_OPEN_CRYPTO_SESSION_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDIARG_OPEN_CRYPTO_SESSION_0030
req.alt-loc: d3d12umddi.h
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

# D3D12DDIARG_OPEN_CRYPTO_SESSION_0030 structure



## -description
Opens a crypto session.



## -syntax

````
typedef struct _D3D12DDIARG_OPEN_CRYPTO_SESSION_0030 {
  CONST VOID *  pPrivateDriverData;
  UINT          PrivateDriverDataSize;
} D3D12DDIARG_OPEN_CRYPTO_SESSION_0030, D3D12DDIARG_OPEN_CRYPTO_SESSION_0030;
````


## -struct-fields

### -field pPrivateDriverData

The private driver data.


### -field PrivateDriverDataSize

The private driver data size.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>