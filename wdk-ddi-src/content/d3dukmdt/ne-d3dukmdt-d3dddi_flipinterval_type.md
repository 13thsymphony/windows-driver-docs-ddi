---
UID: NE:d3dukmdt.D3DDDI_FLIPINTERVAL_TYPE
title: D3DDDI_FLIPINTERVAL_TYPE
author: windows-driver-content
description: The D3DDDI_FLIPINTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.
old-location: display\d3dddi_flipinterval_type.htm
old-project: display
ms.assetid: fbfc270c-b8e3-4467-b99d-2d5932a50114
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_FLIPINTERVAL_FOUR, D3DDDI_FLIPINTERVAL_IMMEDIATE, D3DDDI_FLIPINTERVAL_ONE, D3DDDI_FLIPINTERVAL_THREE, D3DDDI_FLIPINTERVAL_TWO, D3DDDI_FLIPINTERVAL_TYPE, D3DDDI_FLIPINTERVAL_TYPE enumeration [Display Devices], D3D_other_Structs_389c16ef-e25c-498e-994f-324efb96052c.xml, d3dukmdt/D3DDDI_FLIPINTERVAL_FOUR, d3dukmdt/D3DDDI_FLIPINTERVAL_IMMEDIATE, d3dukmdt/D3DDDI_FLIPINTERVAL_ONE, d3dukmdt/D3DDDI_FLIPINTERVAL_THREE, d3dukmdt/D3DDDI_FLIPINTERVAL_TWO, d3dukmdt/D3DDDI_FLIPINTERVAL_TYPE, display.d3dddi_flipinterval_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	D3DDDI_FLIPINTERVAL_TYPE
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_FLIPINTERVAL_TYPE
---

# D3DDDI_FLIPINTERVAL_TYPE Enumeration
The D3DDDI_FLIPINTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.

## Syntax
```
typedef enum D3DDDI_FLIPINTERVAL_TYPE {
  D3DDDI_FLIPINTERVAL_IMMEDIATE                ,
  D3DDDI_FLIPINTERVAL_ONE                      ,
  D3DDDI_FLIPINTERVAL_TWO                      ,
  D3DDDI_FLIPINTERVAL_THREE                    ,
  D3DDDI_FLIPINTERVAL_FOUR                     ,
  D3DDDI_FLIPINTERVAL_IMMEDIATE_ALLOW_TEARING
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3DDDI_FLIPINTERVAL_IMMEDIATE</td>
                    <td>Indicates to perform the flip immediately without waiting for a vertical sync to occur.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_FLIPINTERVAL_ONE</td>
                    <td>Indicates to perform the flip on every vertical sync.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_FLIPINTERVAL_TWO</td>
                    <td>Indicates to perform the flip on every other vertical sync.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_FLIPINTERVAL_THREE</td>
                    <td>Indicates to perform the flip on every third vertical sync.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_FLIPINTERVAL_FOUR</td>
                    <td>Indicates to perform the flip on every fourth vertical sync.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_FLIPINTERVAL_IMMEDIATE_ALLOW_TEARING</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dukmdt.h (include D3dumddi.h, D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557618">DXGKARG_PRESENT</a>