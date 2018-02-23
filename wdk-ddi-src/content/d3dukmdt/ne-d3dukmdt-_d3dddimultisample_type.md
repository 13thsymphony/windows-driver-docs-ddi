---
UID: NE:d3dukmdt._D3DDDIMULTISAMPLE_TYPE
title: "_D3DDDIMULTISAMPLE_TYPE"
author: windows-driver-content
description: The D3DDDIMULTISAMPLE_TYPE enumeration defines the levels of full-scene multisampling that the device can apply.
old-location: display\d3dddimultisample_type.htm
old-project: display
ms.assetid: aba3b4fd-92e4-4551-9396-ee34e38ecfd6
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3dukmdt/D3DDDIMULTISAMPLE_NONMASKABLE, D3DDDIMULTISAMPLE_5_SAMPLES, D3DDDIMULTISAMPLE_11_SAMPLES, display.d3dddimultisample_type, d3dukmdt/D3DDDIMULTISAMPLE_NONE, d3dukmdt/D3DDDIMULTISAMPLE_16_SAMPLES, D3DDDIMULTISAMPLE_4_SAMPLES, d3dukmdt/D3DDDIMULTISAMPLE_9_SAMPLES, DmEnums_e48a95ef-e285-467f-a018-7b5743d3ad8f.xml, d3dukmdt/D3DDDIMULTISAMPLE_11_SAMPLES, D3DDDIMULTISAMPLE_3_SAMPLES, d3dukmdt/D3DDDIMULTISAMPLE_15_SAMPLES, D3DDDIMULTISAMPLE_13_SAMPLES, D3DDDIMULTISAMPLE_7_SAMPLES, D3DDDIMULTISAMPLE_TYPE enumeration [Display Devices], D3DDDIMULTISAMPLE_6_SAMPLES, d3dukmdt/D3DDDIMULTISAMPLE_13_SAMPLES, D3DDDIMULTISAMPLE_8_SAMPLES, D3DDDIMULTISAMPLE_TYPE, d3dukmdt/D3DDDIMULTISAMPLE_8_SAMPLES, d3dukmdt/D3DDDIMULTISAMPLE_4_SAMPLES, d3dukmdt/D3DDDIMULTISAMPLE_10_SAMPLES, D3DDDIMULTISAMPLE_12_SAMPLES, D3DDDIMULTISAMPLE_16_SAMPLES, d3dukmdt/D3DDDIMULTISAMPLE_3_SAMPLES, D3DDDIMULTISAMPLE_2_SAMPLES, d3dukmdt/D3DDDIMULTISAMPLE_2_SAMPLES, d3dukmdt/D3DDDIMULTISAMPLE_6_SAMPLES, d3dukmdt/D3DDDIMULTISAMPLE_7_SAMPLES, D3DDDIMULTISAMPLE_NONE, d3dukmdt/D3DDDIMULTISAMPLE_FORCE_UINT, d3dukmdt/D3DDDIMULTISAMPLE_14_SAMPLES, d3dukmdt/D3DDDIMULTISAMPLE_12_SAMPLES, D3DDDIMULTISAMPLE_15_SAMPLES, D3DDDIMULTISAMPLE_14_SAMPLES, D3DDDIMULTISAMPLE_10_SAMPLES, D3DDDIMULTISAMPLE_NONMASKABLE, _D3DDDIMULTISAMPLE_TYPE, D3DDDIMULTISAMPLE_9_SAMPLES, D3DDDIMULTISAMPLE_FORCE_UINT, d3dukmdt/D3DDDIMULTISAMPLE_TYPE, d3dukmdt/D3DDDIMULTISAMPLE_5_SAMPLES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dukmdt.h
apiname:
-	D3DDDIMULTISAMPLE_TYPE
product: Windows
targetos: Windows
req.typenames: D3DDDIMULTISAMPLE_TYPE
---

# _D3DDDIMULTISAMPLE_TYPE Enumeration
The D3DDDIMULTISAMPLE_TYPE enumeration defines the levels of full-scene multisampling that the device can apply.

## Syntax
````
typedef enum _D3DDDIMULTISAMPLE_TYPE { 
  D3DDDIMULTISAMPLE_NONE         = 0,
  D3DDDIMULTISAMPLE_NONMASKABLE  = 1,
  D3DDDIMULTISAMPLE_2_SAMPLES    = 2,
  D3DDDIMULTISAMPLE_3_SAMPLES    = 3,
  D3DDDIMULTISAMPLE_4_SAMPLES    = 4,
  D3DDDIMULTISAMPLE_5_SAMPLES    = 5,
  D3DDDIMULTISAMPLE_6_SAMPLES    = 6,
  D3DDDIMULTISAMPLE_7_SAMPLES    = 7,
  D3DDDIMULTISAMPLE_8_SAMPLES    = 8,
  D3DDDIMULTISAMPLE_9_SAMPLES    = 9,
  D3DDDIMULTISAMPLE_10_SAMPLES   = 10,
  D3DDDIMULTISAMPLE_11_SAMPLES   = 11,
  D3DDDIMULTISAMPLE_12_SAMPLES   = 12,
  D3DDDIMULTISAMPLE_13_SAMPLES   = 13,
  D3DDDIMULTISAMPLE_14_SAMPLES   = 14,
  D3DDDIMULTISAMPLE_15_SAMPLES   = 15,
  D3DDDIMULTISAMPLE_16_SAMPLES   = 16,
  D3DDDIMULTISAMPLE_FORCE_UINT   = 0x7fffffff
} D3DDDIMULTISAMPLE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_10_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_11_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_12_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_13_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_14_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_15_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_16_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_2_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_3_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_4_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_5_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_6_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_7_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_8_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_9_SAMPLES</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_FORCE_UINT</td>
                    <td>Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. This value is not used.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_NONE</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
            
                <tr>
                    <td>D3DDDIMULTISAMPLE_NONMASKABLE</td>
                    <td>The level of full-scene multisampling available.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dukmdt.h (include D3dukmdt.h) |