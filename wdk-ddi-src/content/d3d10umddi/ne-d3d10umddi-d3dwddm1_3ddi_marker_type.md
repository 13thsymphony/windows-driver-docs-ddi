---
UID: NE:d3d10umddi.D3DWDDM1_3DDI_MARKER_TYPE
title: D3DWDDM1_3DDI_MARKER_TYPE
author: windows-driver-content
description: Indicates the type of marker that the user-mode display driver supports.
old-location: display\d3dwddm1_3ddi_marker_type.htm
old-project: display
ms.assetid: E57CA17F-FB96-4E9B-A38D-67A4F925D3B4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DWDDM1_3DDI_MARKER_TYPE, D3DWDDM1_3DDI_MARKER_TYPE enumeration [Display Devices], D3DWDDM1_3DDI_MARKER_TYPE_NONE, D3DWDDM1_3DDI_MARKER_TYPE_PROFILE, d3d10umddi/D3DWDDM1_3DDI_MARKER_TYPE, d3d10umddi/D3DWDDM1_3DDI_MARKER_TYPE_NONE, d3d10umddi/D3DWDDM1_3DDI_MARKER_TYPE_PROFILE, display.d3dwddm1_3ddi_marker_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3DWDDM1_3DDI_MARKER_TYPE
product: Windows
targetos: Windows
req.typenames: D3DWDDM1_3DDI_MARKER_TYPE
---

# D3DWDDM1_3DDI_MARKER_TYPE Enumeration
Indicates the type of marker that the user-mode display driver supports.

## Syntax
````
typedef enum D3DWDDM1_3DDI_MARKER_TYPE { 
  D3DWDDM1_3DDI_MARKER_TYPE_NONE,
  D3DWDDM1_3DDI_MARKER_TYPE_PROFILE
} D3DWDDM1_3DDI_MARKER_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>D3DWDDM1_3DDI_MARKER_TYPE_NONE</td>
                    <td>No marker type is supported.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM1_3DDI_MARKER_TYPE_PROFILE</td>
                    <td>The context submits GPU work for single-threaded user-mode DDIs. In this case, each time stamp denotes the end of GPU work.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |