---
UID: NS.D3D12UMDDI.D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030
title: D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030
author: windows-driver-content
description: Video decode decryption arguments.
old-location: display\d3d12ddi-video-decode-decryption-arguments-0030.htm
old-project: display
ms.assetid: cdd89f48-1b27-4362-81b3-ed3b89b80b6e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030, D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030
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
req.alt-api: D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030
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

# D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030 structure



## -description
Video decode decryption arguments.


## -syntax

````
typedef struct _D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030 {
  D3D12DDI_HCRYPTOSESSIONPOLICY_0030  hDrvCryptoSessionPolicy;
  CONST VOID *                        pIV;
  UINT                                IVSize;
  CONST VOID *                        pSubSampleMappingBlock;
  UINT                                SubSampleMappingCount;
} D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030, D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030;
````


## -struct-fields

### -field hDrvCryptoSessionPolicy

Crypto session policy.

### -field pIV

Initialization vector.

### -field IVSize

Initialization vector size.

### -field pSubSampleMappingBlock

Sub sample mapping block.

### -field SubSampleMappingCount

Sub sample mapping count.

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