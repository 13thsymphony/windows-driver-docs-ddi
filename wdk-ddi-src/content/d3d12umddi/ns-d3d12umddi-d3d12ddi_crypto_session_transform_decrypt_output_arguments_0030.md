---
UID: NS.D3D12UMDDI.D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_OUTPUT_ARGUMENTS_0030
title: D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_OUTPUT_ARGUMENTS_0030
author: windows-driver-content
description: Crypt session transform decrypt output arguments.
old-location: display\d3d12ddi-crypto-session-transform-decrypt-output-arguments-0030.htm
old-project: display
ms.assetid: 08ee50fd-d56f-4dbe-9e1c-17333a258861
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_OUTPUT_ARGUMENTS_0030, D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_OUTPUT_ARGUMENTS_0030
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
req.alt-api: D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_OUTPUT_ARGUMENTS_0030
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

# D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_OUTPUT_ARGUMENTS_0030 structure



## -description
Crypt session transform decrypt output arguments.


## -syntax

````
typedef struct _D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_OUTPUT_ARGUMENTS_0030 {
  BOOL                Enable;
  D3D12DDI_HRESOURCE  hDrvBuffer;
  UINT64              Size;
  UINT64              Offset;
} D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_OUTPUT_ARGUMENTS_0030, D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_OUTPUT_ARGUMENTS_0030;
````


## -struct-fields

### -field Enable

Enable.

### -field hDrvBuffer

Buffer.

### -field Size

Size.

### -field Offset

Offset.

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