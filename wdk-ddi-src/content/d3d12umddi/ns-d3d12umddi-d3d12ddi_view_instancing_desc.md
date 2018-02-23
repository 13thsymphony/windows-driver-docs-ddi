---
UID: NS:d3d12umddi.D3D12DDI_VIEW_INSTANCING_DESC
title: D3D12DDI_VIEW_INSTANCING_DESC
author: windows-driver-content
description: View instancing description.
old-location: display\d3d12ddi-view-instancing-desc.htm
old-project: display
ms.assetid: 4d942de6-d829-499c-80cf-3cff8266aee4
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3D12DDI_VIEW_INSTANCING_DESC structure [Display Devices], d3d12umddi/D3D12DDI_VIEW_INSTANCING_DESC, display.d3d12ddi-view-instancing-desc, D3D12DDI_VIEW_INSTANCING_DESC
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
-	D3D12DDI_VIEW_INSTANCING_DESC
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIEW_INSTANCING_DESC
---

# D3D12DDI_VIEW_INSTANCING_DESC structure
View instancing description.

## Syntax
````
typedef struct _D3D12DDI_VIEW_INSTANCING_DESC {
  UINT                                     ViewInstanceCount;
  const D3D12DDI_VIEW_INSTANCE_LOCATION *  pViewInstanceLocations;
  D3D12DDI_VIEW_INSTANCING_FLAGS           Flags;
} D3D12DDI_VIEW_INSTANCING_DESC, D3D12DDI_VIEW_INSTANCING_DESC;
````

## Members


`Flags`

Flags.

`pViewInstanceLocations`

View instance locations.

`ViewInstanceCount`

View instance count.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |