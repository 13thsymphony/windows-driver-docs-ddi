---
UID: NE:d3dkmdt._D3DKMDT_MONITOR_ORIENTATION
title: "_D3DKMDT_MONITOR_ORIENTATION"
author: windows-driver-content
description: The D3DKMDT_MONITOR_ORIENTATION enumeration is used to describe the orientation (rotation angle) of a connected external display device.
old-location: display\d3dkmdt_monitor_orientation.htm
old-project: display
ms.assetid: 16e7d91c-04de-4a8c-97c2-c500d0d3697d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmdt/D3DKMDT_MO_UNINITIALIZED, D3DKMDT_MO_270DEG, d3dkmdt/D3DKMDT_MO_180DEG, d3dkmdt/D3DKMDT_MO_0DEG, D3DKMDT_MONITOR_ORIENTATION enumeration [Display Devices], D3DKMDT_MO_0DEG, d3dkmdt/D3DKMDT_MO_270DEG, d3dkmdt/D3DKMDT_MONITOR_ORIENTATION, D3DKMDT_MO_90DEG, d3dkmdt/D3DKMDT_MO_90DEG, D3DKMDT_MO_UNINITIALIZED, display.d3dkmdt_monitor_orientation, D3DKMDT_MONITOR_ORIENTATION, _D3DKMDT_MONITOR_ORIENTATION, D3DKMDT_MO_180DEG, DmEnums_d8dfc33b-5b13-4fb0-8ef4-091c5b018424.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	D3DKMDT_MONITOR_ORIENTATION
product: Windows
targetos: Windows
req.typenames: D3DKMDT_MONITOR_ORIENTATION
---

# _D3DKMDT_MONITOR_ORIENTATION Enumeration
The D3DKMDT_MONITOR_ORIENTATION enumeration is used to describe the orientation (rotation angle) of a connected external display device.

## Syntax
````
typedef enum _D3DKMDT_MONITOR_ORIENTATION { 
  D3DKMDT_MO_UNINITIALIZED  = 0,
  D3DKMDT_MO_0DEG           = 1,
  D3DKMDT_MO_90DEG          = 2,
  D3DKMDT_MO_180DEG         = 3,
  D3DKMDT_MO_270DEG         = 4
} D3DKMDT_MONITOR_ORIENTATION;
````

## Constants

<table>
            
                <tr>
                    <td>D3DKMDT_MO_0DEG</td>
                    <td>Indicates that the display device has not been rotated from its default orientation.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_MO_180DEG</td>
                    <td>Indicates that the display device has been rotated 180 degrees clockwise from its default orientation.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_MO_270DEG</td>
                    <td>Indicates that the display device has been rotated 270 degrees clockwise from its default orientation.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_MO_90DEG</td>
                    <td>Indicates that the display device has been rotated 90 degrees clockwise from its default orientation.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_MO_UNINITIALIZED</td>
                    <td>Indicates that a variable of type D3DKMDT_MONITOR_ORIENTATION has not yet been assigned a meaningful value.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |