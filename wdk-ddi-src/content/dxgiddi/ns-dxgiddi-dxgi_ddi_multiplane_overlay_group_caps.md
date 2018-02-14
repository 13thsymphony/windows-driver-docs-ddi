---
UID: NS:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS
title: DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS
author: windows-driver-content
description: Used by the user-mode display driver to specify groups of overlay plane capabilities.
old-location: display\dxgi_ddi_multiplane_overlay_group_caps.htm
old-project: display
ms.assetid: A8BAD8D4-1009-43D0-B82F-8252062A029C
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS, DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS structure [Display Devices], display.dxgi_ddi_multiplane_overlay_group_caps, DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Dxgiddi.h
apiname:
-	DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS
---

# DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS structure
Used by the user-mode display driver to specify groups of overlay plane capabilities.

## Syntax
````
typedef struct _DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS {
  UINT  NumPlanes;
  float MaxStretchFactor;
  float MaxShrinkFactor;
  UINT  OverlayCaps;
  UINT  StereoCaps;
} DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS;
````

## Members


`MaxShrinkFactor`

Specifies the maximum shrink factor that is supported by the overlay planes within the capability group.

The shrink factor is the ratio of the final, shrunk overlay plane size to the original size. For example, if the original overlay plane is 100 x 100 pixels, a value of 0.25 means that it can be shrunk to 25 x 25 pixels.

It's not guaranteed that this shrink factor can be applied in all scenarios. For example, it might be possible to shrink only one overlay plane out of several using this factor.

`MaxStretchFactor`

Specifies the maximum stretch factor that is supported by the overlay planes within the capability group.

The stretch factor is the ratio of the final, stretched overlay plane size to the original size. For example, if the original overlay plane is 100 x 100 pixels, a value of 2.5 means that it can be stretched to 250 x 250 pixels.

It's not guaranteed that this stretch factor can be applied in all scenarios. For example, it might be possible to stretch only one overlay plane out of several using this factor.

`NumPlanes`

Specifies the number of overlay planes that are supported by the overlay planes within the capability group.

`OverlayCaps`

The overlay capabilities, given as a bitwise <b>OR</b> of values from the <a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_multiplane_overlay_feature_caps.md">DXGI_DDI_MULTIPLANE_OVERLAY_FEATURE_CAPS</a> enumeration.

`StereoCaps`

Reserved for system use. Set this value to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | dxgiddi.h (include D3d10umddi.h) |