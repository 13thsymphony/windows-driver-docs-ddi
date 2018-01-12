---
UID: NS:d3d12umddi.D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030
title: D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030
author: windows-driver-content
description: Crypto session transform input arguments.
old-location: display\d3d12ddi-crypto-session-transform-input-arguments-0030.htm
old-project: display
ms.assetid: 2c7e1218-63d3-4fa5-8b02-7bee5920146c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030, D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030
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
req.alt-api: D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030
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
req.typenames: D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030
---

# D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030 structure



## -description
Crypto session transform input arguments.



## -syntax

````
typedef struct _D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030 {
  D3D12DDI_HCRYPTOSESSIONPOLICY_0030                                     hDrvCryptoSessionPolicy;
  D3D12DDI_HRESOURCE                                                     hDrvBuffer;
  UINT64                                                                 Size;
  UINT64                                                                 Offset;
  const void *                                                           pIV;
  UINT                                                                   IVSize;
  const void *                                                           pSubSampleMappingBlock;
  UINT                                                                   SubSampleMappingCount;
  const void *                                                           pContext;
  UINT64                                                                 ContextSize;
  D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030  EncryptedHeader;
} D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030, D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030;
````


## -struct-fields

### -field hDrvCryptoSessionPolicy

Crypto session policy.


### -field hDrvBuffer

Resource.


### -field Size

Size.


### -field Offset

Offset.


### -field pIV

Initialization vector.


### -field IVSize

Initialization vector size.


### -field pSubSampleMappingBlock

Sub sample mapping block.


### -field SubSampleMappingCount

Sub sample mapping count.


### -field pContext

Context.


### -field ContextSize

Context size.


### -field EncryptedHeader

Encrypted header.


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