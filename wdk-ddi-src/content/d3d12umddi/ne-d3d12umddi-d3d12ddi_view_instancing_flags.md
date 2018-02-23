---
UID: NE:d3d12umddi.D3D12DDI_VIEW_INSTANCING_FLAGS
title: D3D12DDI_VIEW_INSTANCING_FLAGS
author: windows-driver-content
description: Defines the view instancing flags.
old-location: display\d3d12ddi-view-instancing-flags.htm
old-project: display
ms.assetid: fa44933f-aa3b-466a-8ee2-2d34d0311562
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3D12DDI_VIEW_INSTANCING_FLAGS enumeration [Display Devices], D3D12DDI_VIEW_INSTANCING_FLAG_NONE, d3d12umddi/D3D12DDI_VIEW_INSTANCING_FLAG_ENABLE_VIEW_INSTANCE_MASKING, D3D12DDI_VIEW_INSTANCING_FLAGS, D3D12DDI_VIEW_INSTANCING_FLAG_ENABLE_VIEW_INSTANCE_MASKING, d3d12umddi/D3D12DDI_VIEW_INSTANCING_FLAG_NONE, display.d3d12ddi-view-instancing-flags, d3d12umddi/D3D12DDI_VIEW_INSTANCING_FLAGS
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
-	D3D12DDI_VIEW_INSTANCING_FLAGS
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIEW_INSTANCING_FLAGS
---

# D3D12DDI_VIEW_INSTANCING_FLAGS Enumeration
Defines the view instancing flags.

## Syntax
````
typedef enum _D3D12DDI_VIEW_INSTANCING_FLAGS { 
  D3D12DDI_VIEW_INSTANCING_FLAG_NONE,
  D3D12DDI_VIEW_INSTANCING_FLAG_ENABLE_VIEW_INSTANCE_MASKING
} D3D12DDI_VIEW_INSTANCING_FLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_VIEW_INSTANCING_FLAG_ENABLE_VIEW_INSTANCE_MASKING</td>
                    <td>The view instancing flag is enable view instance masking.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIEW_INSTANCING_FLAG_NONE</td>
                    <td>No view instancing flag is defined.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |