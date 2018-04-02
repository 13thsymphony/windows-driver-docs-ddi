---
UID: NE:d3dukmdt.D3DDDI_SCANLINEORDERING
title: D3DDDI_SCANLINEORDERING
author: windows-driver-content
description: The D3DDDI_SCANLINEORDERING enumeration type contains values that identify how the scan lines are drawn on a surface.
old-location: display\d3dddi_scanlineordering.htm
old-project: display
ms.assetid: 6b7b0bbf-79f2-4b0c-a7e6-75dc92bf8a63
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_SCANLINEORDERING, D3DDDI_SCANLINEORDERING enumeration [Display Devices], D3DDDI_SCANLINEORDERING_INTERLACED, D3DDDI_SCANLINEORDERING_PROGRESSIVE, D3DDDI_SCANLINEORDERING_UNKNOWN, D3D_other_Structs_e1e24d3b-d40e-4f20-bd78-94ab7c2d0761.xml, d3dukmdt/D3DDDI_SCANLINEORDERING, d3dukmdt/D3DDDI_SCANLINEORDERING_INTERLACED, d3dukmdt/D3DDDI_SCANLINEORDERING_PROGRESSIVE, d3dukmdt/D3DDDI_SCANLINEORDERING_UNKNOWN, display.d3dddi_scanlineordering
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDI_SCANLINEORDERING is supported beginning with the Windows 7 operating system.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	D3DDDI_SCANLINEORDERING
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_SCANLINEORDERING
---

# D3DDDI_SCANLINEORDERING Enumeration
The D3DDDI_SCANLINEORDERING enumeration type contains values that identify how the scan lines are drawn on a surface.

## Syntax
```
typedef enum D3DDDI_SCANLINEORDERING {
  D3DDDI_SCANLINEORDERING_UNKNOWN      ,
  D3DDDI_SCANLINEORDERING_PROGRESSIVE  ,
  D3DDDI_SCANLINEORDERING_INTERLACED
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3DDDI_SCANLINEORDERING_UNKNOWN</td>
                    <td>The value indicates that scan-line ordering is unknown.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_SCANLINEORDERING_PROGRESSIVE</td>
                    <td>The value indicates that scan-line ordering is progressive.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_SCANLINEORDERING_INTERLACED</td>
                    <td>The value indicates that scan-line ordering is interlaced.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DDDI_SCANLINEORDERING is supported beginning with the Windows 7 operating system. D3DDDI_SCANLINEORDERING is supported beginning with the Windows 7 operating system. |
| **Header** | d3dukmdt.h (include D3dumddi.h, D3dkmddi.h) |