---
UID: NE:d3d10umddi.D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS
title: D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS
author: windows-driver-content
description: Used by the CheckDirectFlipFlags parameter of the CheckDirectFlipSupport(D3D11_1) function to specify seamless flipping of video memory.
old-location: display\d3d11_1_ddi_check_direct_flip_flags.htm
old-project: display
ms.assetid: beead760-8f93-48da-b2fc-2f8a0031019c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE, D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS, D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS enumeration [Display Devices], d3d10umddi/D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE, d3d10umddi/D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS, display.d3d11_1_ddi_check_direct_flip_flags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS
product:
- Windows
targetos: Windows
req.typenames: D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS
---

# D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS Enumeration
Used by the <i>CheckDirectFlipFlags</i> parameter of the <a href="https://msdn.microsoft.com/2acf84cb-5e51-4aa8-96ce-96abc6ceec8c">CheckDirectFlipSupport(D3D11_1)</a> function to specify seamless flipping of video memory.

## Syntax
```
typedef enum D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS {
  D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE</td>
                    <td>Seamless flipping should occur immediately and does not have to be synchronized with a VSync interrupt.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/2acf84cb-5e51-4aa8-96ce-96abc6ceec8c">CheckDirectFlipSupport(D3D11_1)</a>