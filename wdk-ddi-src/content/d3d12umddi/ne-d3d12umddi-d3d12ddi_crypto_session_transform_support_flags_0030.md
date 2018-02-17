---
UID: NE:d3d12umddi.D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030
title: D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030
author: windows-driver-content
description: The crypto session transform support flags.
old-location: display\d3d12ddi-crypto-session-transform-support-flags-0030.htm
old-project: display
ms.assetid: 9b8fea62-9947-42ce-acb6-1736ac6e3d86
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030, D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAG_0030_SUPPORTED, d3d12umddi/D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAG_0030_SUPPORTED, d3d12umddi/D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAG_0030_NONE, D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAG_0030_NONE, D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030 enumeration [Display Devices], d3d12umddi/D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030, display.d3d12ddi-crypto-session-transform-support-flags-0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030
---

# D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030 Enumeration
The crypto session transform support flags.

## Syntax
````
typedef enum _D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030 { 
  D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAG_0030_NONE,
  D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAG_0030_SUPPORTED
} D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030;
````

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAG_0030_NONE</td>
                    <td>A crypto session transform support flag is not available.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAG_0030_SUPPORTED</td>
                    <td>The crypto session transform support flag is supported.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |