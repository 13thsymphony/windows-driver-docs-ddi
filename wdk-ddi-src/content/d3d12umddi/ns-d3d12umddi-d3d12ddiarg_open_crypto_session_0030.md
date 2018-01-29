---
UID : NS:d3d12umddi.D3D12DDIARG_OPEN_CRYPTO_SESSION_0030
title : D3D12DDIARG_OPEN_CRYPTO_SESSION_0030
author : windows-driver-content
description : Opens a crypto session.
old-location : display\d3d12ddiarg-open-crypto-session-0030.htm
old-project : display
ms.assetid : 8b500956-6d22-4862-b9e4-e3cb545fcc0e
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3d12umddi/D3D12DDIARG_OPEN_CRYPTO_SESSION_0030, display.d3d12ddiarg-open-crypto-session-0030, D3D12DDIARG_OPEN_CRYPTO_SESSION_0030, D3D12DDIARG_OPEN_CRYPTO_SESSION_0030 structure [Display Devices]
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3D12DDIARG_OPEN_CRYPTO_SESSION_0030
---

# D3D12DDIARG_OPEN_CRYPTO_SESSION_0030 structure
Opens a crypto session.

## Syntax
````
typedef struct _D3D12DDIARG_OPEN_CRYPTO_SESSION_0030 {
  CONST VOID *  pPrivateDriverData;
  UINT          PrivateDriverDataSize;
} D3D12DDIARG_OPEN_CRYPTO_SESSION_0030, D3D12DDIARG_OPEN_CRYPTO_SESSION_0030;
````

## Members


`pPrivateDriverData`

The private driver data.

`PrivateDriverDataSize`

The private driver data size.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h |