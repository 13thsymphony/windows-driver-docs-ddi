---
UID: NS:dxgiddi.DXGI_DDI_RATIONAL
title: DXGI_DDI_RATIONAL
author: windows-driver-content
description: The DXGI_DDI_RATIONAL structure describes a fractional value that represents vertical and horizontal frequencies of a display mode (that is, vertical sync and horizontal sync).
old-location: display\dxgi_ddi_rational.htm
old-project: display
ms.assetid: 3a1ebeb8-4a0e-4a1f-9039-13ca8e375e5e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGI_DDI_RATIONAL, DXGI_DDI_RATIONAL structure [Display Devices], UMDisplayDriver_Dx10param_Structs_ef68ce24-ab05-45db-9b37-02367bbba7f4.xml, display.dxgi_ddi_rational, dxgiddi/DXGI_DDI_RATIONAL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
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
-	dxgiddi.h
api_name:
-	DXGI_DDI_RATIONAL
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_RATIONAL
---

# DXGI_DDI_RATIONAL structure
The DXGI_DDI_RATIONAL structure describes a fractional value that represents vertical and horizontal frequencies of a display mode (that is, vertical sync and horizontal sync).

## Syntax
````
typedef struct DXGI_DDI_RATIONAL {
  UINT Numerator;
  UINT Denominator;
} DXGI_DDI_RATIONAL;
````

## Members


`Numerator`

[in] The numerator of the frequency fraction.

`Denominator`

[in] The denominator of the frequency fraction.

## Remarks
Vertical frequencies are stored in Hertz (Hz); horizontal frequencies are stored in kilohertz (kHz). The dynamic range of this encoding format, given 10^-7 resolution, is {0..(2^32 - 1) / 10^7}. This range translates to {0..428.4967296} [Hz] for vertical frequencies and {0..428.4967296} [kHz] for horizontal frequencies. This submicrosecond precision range is acceptable even for a provided application. (An error of one microsecond for video signal synchronization would imply a time drift with a cycle of 10^7/(60 x 60 x 24) = 115.741 days.)

For a rational number with a finite fractional sequence, use a denominator of the form 10^(length of fractional sequence). For a rational number without a finite fractional sequence, a sequence that exceeds the precision that the dynamic range of the denominator allows, or an irrational number, use an appropriate ratio of integers that best represents the value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dxgiddi.h (include D3d10umddi.h) |

## See Also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_mode_desc.md">DXGI_DDI_MODE_DESC</a>