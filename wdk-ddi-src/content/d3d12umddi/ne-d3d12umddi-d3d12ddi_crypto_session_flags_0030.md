---
UID : NE:d3d12umddi.D3D12DDI_CRYPTO_SESSION_FLAGS_0030
title : D3D12DDI_CRYPTO_SESSION_FLAGS_0030
author : windows-driver-content
description : The crypto session flags.
old-location : display\d3d12ddi-crypto-session-flags-0030.htm
old-project : display
ms.assetid : 0a799227-9b37-45f6-bded-e56c439e465f
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_CRYPTO_SESSION_FLAGS_0030, D3D12DDI_CRYPTO_SESSION_FLAGS_0030
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3d12umddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D12DDI_CRYPTO_SESSION_FLAGS_0030
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
req.typenames : D3D12DDI_CRYPTO_SESSION_FLAGS_0030
---

# D3D12DDI_CRYPTO_SESSION_FLAGS_0030 Enumeration
The crypto session flags.

## Syntax
````
typedef enum _D3D12DDI_CRYPTO_SESSION_FLAGS_0030 { 
  D3D12DDI_CRYPTO_SESSION_FLAG_0030_NONE,
  D3D12DDI_CRYPTO_SESSION_FLAG_0030_HARDWARE
} D3D12DDI_CRYPTO_SESSION_FLAGS_0030;
````

## Constants

<table>

<tr>
<td>D3D12DDI_CRYPTO_SESSION_FLAG_0030_HARDWARE</td>
<td>The crypto session flag is of type hardware.</td>
</tr>

<tr>
<td>D3D12DDI_CRYPTO_SESSION_FLAG_0030_NONE</td>
<td>No crypto session flag is defined.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h |