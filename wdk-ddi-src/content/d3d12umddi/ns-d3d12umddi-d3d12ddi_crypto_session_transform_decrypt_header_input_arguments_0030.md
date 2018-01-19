---
UID : NS:d3d12umddi.D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030
title : D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030
author : windows-driver-content
description : Crypto session transform decrypt header input arguments.
old-location : display\d3d12ddi-crypto-session-transform-decrypt-header-input-arguments-0030.htm
old-project : display
ms.assetid : 49367166-11bd-4a4e-aa47-e91dbe9a3df8
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030, D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d12umddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030
req.alt-loc : d3d12umddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030
---

# D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030 structure
Crypto session transform decrypt header input arguments.

## Syntax
````
typedef struct _D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030 {
  BOOL           Enable;
  const void *   pSliceHeaders;
  UINT64         SliceHeadersSize;
  const DWORD *  pSliceHeadersOffsets;
  UINT64         SliceHeaderCount;
  const void *   pContext;
  UINT64         ContextSize;
} D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030, D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030;
````

## Members

        
            `ContextSize`

            Context size.
        
            `Enable`

            Enable.
        
            `pContext`

            Context.
        
            `pSliceHeaders`

            Slice headers.
        
            `pSliceHeadersOffsets`

            Slice header offsets.
        
            `SliceHeaderCount`

            Slice header count.
        
            `SliceHeadersSize`

            Slice header size.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h |