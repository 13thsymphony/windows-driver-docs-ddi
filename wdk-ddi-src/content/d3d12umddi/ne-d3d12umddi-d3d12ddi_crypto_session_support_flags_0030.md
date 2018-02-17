---
UID: NE:d3d12umddi.D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030
title: D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030
author: windows-driver-content
description: The crypto session support flags.
old-location: display\d3d12ddi-crypto-session-support-flags-0030.htm
old-project: display
ms.assetid: ffa81a22-3de2-48f8-b753-c296401e0da3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_SUPPORTED, d3d12umddi/D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_HEADER_DECRYPTION_REQUIRED, D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_NONE, D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_HEADER_DECRYPTION_REQUIRED, D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030, d3d12umddi/D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_NONE, D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_TRANSCRYPTION_REQUIRED, d3d12umddi/D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_TRANSCRYPTION_REQUIRED, D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_INDEPENDENT_DECRYPTION_REQUIRED, D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030 enumeration [Display Devices], d3d12umddi/D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_SUPPORTED, display.d3d12ddi-crypto-session-support-flags-0030, d3d12umddi/D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_INDEPENDENT_DECRYPTION_REQUIRED, d3d12umddi/D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030
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
-	D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030
---

# D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030 Enumeration
The crypto session support flags.

## Syntax
````
typedef enum _D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030 { 
  D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_NONE,
  D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_SUPPORTED,
  D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_HEADER_DECRYPTION_REQUIRED,
  D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_INDEPENDENT_DECRYPTION_REQUIRED,
  D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_TRANSCRYPTION_REQUIRED
} D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030;
````

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_HEADER_DECRYPTION_REQUIRED</td>
                    <td>The crypto session support flag requires a header decryption.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_INDEPENDENT_DECRYPTION_REQUIRED</td>
                    <td>The crypto session support flag requires an independent decyption.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_NONE</td>
                    <td>No flag is defined.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_SUPPORTED</td>
                    <td>The crypto session support flag is supported.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_TRANSCRYPTION_REQUIRED</td>
                    <td>The crypto session support flag requires transcryption.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |