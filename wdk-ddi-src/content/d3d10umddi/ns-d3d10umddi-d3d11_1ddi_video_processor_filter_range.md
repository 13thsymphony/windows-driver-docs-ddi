---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE
title: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE
author: windows-driver-content
description: Defines the range of supported values for an image filter.
old-location: display\d3d11_1ddi_video_processor_filter_range.htm
old-project: display
ms.assetid: 9dc93d92-ccdc-488b-a5dd-a2efe783cbb3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d11_1ddi_video_processor_filter_range, D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE structure [Display Devices], D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE
---

# D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE structure
Defines the range of supported values for an image filter.

## Syntax
````
typedef struct D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE {
  int   Minimum;
  int   Maximum;
  int   Default;
  float Multiplier;
} D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE;
````

## Members


`Default`

The default value of the filter.

`Maximum`

The maximum value of the filter.

`Minimum`

The minimum value of the filter.

`Multiplier`

A multiplier. Use the following formula to translate the filter setting into the actual filter value: <i>Actual Value</i> = <i>Set Value</i> Ã— <i>Multiplier</i>.

## Remarks
The multiplier enables the filter range to have a fractional step value.

For example, a hue filter might have an actual range of [â€“180.0 … +180.0] with a step size of 0.25. The device would report the following range and multiplier:<ul>
<li>Minimum: â€“720</li>
<li>Maximum: +720</li>
<li>Multiplier: 0.25</li>
</ul>


In this case, a filter value of 2 would be interpreted by the device as 0.50 (or 2 Ã— 0.25).

The device should use a multiplier that can be represented exactly as a base-2 fraction.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |