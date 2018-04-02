---
UID: NS:d3dkmddi._DXGK_INHERITED_TIMING_INFO
title: "_DXGK_INHERITED_TIMING_INFO"
author: windows-driver-content
description: Structure passed to the driver in the pPrivateDriverData argument of DxgkDdiRecommendFunctionalVidPn, which the driver should use to describe the color space and wire format which cannot be described easily in the VidPn the DDI builds.
old-location: display\dxgk_inherited_timing_info.htm
old-project: display
ms.assetid: 8A5CB3A6-970C-448D-8808-F072EE67BCA3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDXGK_INHERITED_TIMING_INFO, DXGK_INHERITED_TIMING_INFO, DXGK_INHERITED_TIMING_INFO structure [Display Devices], PDXGK_INHERITED_TIMING_INFO, PDXGK_INHERITED_TIMING_INFO structure pointer [Display Devices], _DXGK_INHERITED_TIMING_INFO, d3dkmddi/DXGK_INHERITED_TIMING_INFO, d3dkmddi/PDXGK_INHERITED_TIMING_INFO, display.dxgk_inherited_timing_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_INHERITED_TIMING_INFO
product:
- Windows
targetos: Windows
req.typenames: DXGK_INHERITED_TIMING_INFO, *PDXGK_INHERITED_TIMING_INFO
---

# _DXGK_INHERITED_TIMING_INFO structure
Structure passed to the driver in the pPrivateDriverData argument of DxgkDdiRecommendFunctionalVidPn, which the driver should use to describe the color space and wire format which cannot be described easily in the VidPn the DDI builds

## Syntax
```
typedef struct _DXGK_INHERITED_TIMING_INFO {
  union {
    D3DDDI_COLOR_SPACE_TYPE             OutputColorSpace;
    D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE OutputWireColorSpace;
  };
  D3DKMDT_WIRE_FORMAT_AND_PREFERENCE SelectedWireFormat;
  union {
    struct {
      DXGK_GLITCH_CAUSE    GlitchCause;
      DXGK_GLITCH_EFFECT   GlitchEffect;
      DXGK_GLITCH_DURATION GlitchDuration;
      UINT8                Reserved;
    };
    UINT DiagnosticInfo;
  };
} DXGK_INHERITED_TIMING_INFO, *PDXGK_INHERITED_TIMING_INFO;
```

## Members


`SelectedWireFormat`

A D3DKMDT_WIRE_FORMAT_AND_PREFERENCE value which indicates the wire format which is actually being used.  Although the target mode pinned in the VidPn returned by the call to DxgkDdiRecommendFunctionalVidPn could be required to describe exactly one wire format, that might require the driver to prepare a special target mode just for the boot case.  Instead, this field should be used to report the current wire color encoding format and bits per color channel.  Whichever format is reported in this field should also have been reported as supported in the target mode reported through DxgkDdiRecommendFunctionalVidPn.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |