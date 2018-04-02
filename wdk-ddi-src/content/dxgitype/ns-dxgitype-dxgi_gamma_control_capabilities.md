---
UID: NS:dxgitype.DXGI_GAMMA_CONTROL_CAPABILITIES
title: DXGI_GAMMA_CONTROL_CAPABILITIES
author: windows-driver-content
description: The DXGI_GAMMA_CONTROL_CAPABILIITES structure describes gamma capabilities.
old-location: display\dxgi_gamma_control_capabiliites.htm
old-project: display
ms.assetid: 7a91311e-c8b9-4f28-b72e-9f93d459aac2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGI_GAMMA_CONTROL_CAPABILIITES, DXGI_GAMMA_CONTROL_CAPABILIITES structure [Display Devices], DXGI_GAMMA_CONTROL_CAPABILITIES, DXGI_GAMMA_CONTROL_CAPABILITIES structure [Display Devices], UMDisplayDriver_Dx10param_Structs_002eb4f0-081a-43df-a307-e979017daf6f.xml, display.dxgi_gamma_control_capabiliites, dxgitype/DXGI_GAMMA_CONTROL_CAPABILIITES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgitype.h
req.include-header: D3d10umddi.h
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
-	Dxgitype.h
api_name:
-	DXGI_GAMMA_CONTROL_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: DXGI_GAMMA_CONTROL_CAPABILITIES
---

# DXGI_GAMMA_CONTROL_CAPABILITIES structure
The DXGI_GAMMA_CONTROL_CAPABILIITES structure describes gamma capabilities.

## Syntax
```
typedef struct DXGI_GAMMA_CONTROL_CAPABILITIES {
  BOOL  ScaleAndOffsetSupported;
  float MaxConvertedValue;
  float MinConvertedValue;
  UINT  NumGammaControlPoints;
  float ControlPointPositions[1025];
};
```

## Members


`ScaleAndOffsetSupported`

[out] A BOOL value that indicates whether the device supports scale and offset. <b>TRUE</b> indicates that the device supports scale and offset; <b>FALSE</b> indicates that the device does not support scale and offset.

`MaxConvertedValue`

[out] A single-precision float vector for the maximum converted value for the gamma control.

`MinConvertedValue`

[out] A single-precision float vector for the minimum converted value for the gamma control.

`NumGammaControlPoints`

[out] The number of elements in the array that the <b>ControlPointPositions</b> member specifies.

`ControlPointPositions`

[out] An array of single-precision float vectors that describe the gamma control point positions.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dxgitype.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557455">DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566790">GetGammaCapsDXGI</a>