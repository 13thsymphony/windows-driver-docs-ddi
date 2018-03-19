---
UID: NE:d3dumddi._DXVAHDDDI_ROTATION
title: "_DXVAHDDDI_ROTATION"
author: windows-driver-content
description: Specifies the clockwise rotation of the display output surface.
old-location: display\dxvahdddi_rotation.htm
old-project: display
ms.assetid: 667f1c5e-c342-40b2-b215-2538669288cc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVAHDDDI_ROTATION, DXVAHDDDI_ROTATION enumeration [Display Devices], DXVAHDDDI_ROTATION_180, DXVAHDDDI_ROTATION_270, DXVAHDDDI_ROTATION_90, DXVAHDDDI_ROTATION_IDENTITY, _DXVAHDDDI_ROTATION, d3dumddi/DXVAHDDDI_ROTATION, d3dumddi/DXVAHDDDI_ROTATION_180, d3dumddi/DXVAHDDDI_ROTATION_270, d3dumddi/DXVAHDDDI_ROTATION_90, d3dumddi/DXVAHDDDI_ROTATION_IDENTITY, display.dxvahdddi_rotation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	D3dumddi.h
api_name:
-	DXVAHDDDI_ROTATION
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_ROTATION
---

# _DXVAHDDDI_ROTATION Enumeration
Specifies the clockwise rotation of the display output surface.

## Syntax
````
typedef enum _DXVAHDDDI_ROTATION { 
  DXVAHDDDI_ROTATION_IDENTITY  = 0,
  DXVAHDDDI_ROTATION_90        = 1,
  DXVAHDDDI_ROTATION_180       = 2,
  DXVAHDDDI_ROTATION_270       = 3
} DXVAHDDDI_ROTATION;
````

## Constants

<table>
            
                <tr>
                    <td>DXVAHDDDI_ROTATION_IDENTITY</td>
                    <td>Indicates that rotation is 0 degrees—landscape mode.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_ROTATION_90</td>
                    <td>Indicates that rotation is 90 degrees clockwise—portrait mode.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_ROTATION_180</td>
                    <td>Indicates that rotation is 180 degrees clockwise—inverted landscape mode.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_ROTATION_270</td>
                    <td>Indicates that rotation is 270 degrees clockwise—inverted portrait mode.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dumddi.h (include D3dumddi.h) |