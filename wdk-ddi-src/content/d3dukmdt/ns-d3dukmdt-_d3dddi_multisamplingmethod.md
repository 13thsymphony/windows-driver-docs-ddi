---
UID: NS:d3dukmdt._D3DDDI_MULTISAMPLINGMETHOD
title: "_D3DDDI_MULTISAMPLINGMETHOD"
author: windows-driver-content
description: The D3DDDI_MULTISAMPLINGMETHOD structure describes a multiple-sampling method.
old-location: display\d3dddi_multisamplingmethod.htm
old-project: display
ms.assetid: 2838cb87-0cd5-4351-a477-00f75eca0896
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_MULTISAMPLINGMETHOD, D3DDDI_MULTISAMPLINGMETHOD structure [Display Devices], D3D_other_Structs_752f8e91-d298-437a-80c4-005e21ec0ddd.xml, _D3DDDI_MULTISAMPLINGMETHOD, d3dukmdt/D3DDDI_MULTISAMPLINGMETHOD, display.d3dddi_multisamplingmethod
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
-	d3dukmdt.h
api_name:
-	D3DDDI_MULTISAMPLINGMETHOD
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_MULTISAMPLINGMETHOD
---

# _D3DDDI_MULTISAMPLINGMETHOD structure
The D3DDDI_MULTISAMPLINGMETHOD structure describes a multiple-sampling method.

## Syntax
```
typedef struct _D3DDDI_MULTISAMPLINGMETHOD {
  UINT NumSamples;
  UINT NumQualityLevels;
} D3DDDI_MULTISAMPLINGMETHOD;
```

## Members


`NumSamples`

[out] The number of subpixels that are used in the multiple-sampling method (for example, 2 for 2x and 8 for 8x multiple-sampling).

`NumQualityLevels`

[out] The upper bound on the quality range that is supported for the multiple-sampling method. The range includes values from 0 through the reported maximum quality setting.

## Remarks
The driver can partition its quality levels for a given multiple-sampling method into as many increments as it requires; however, each incremental step noticeably improves quality of the presented image.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dukmdt.h (include D3dumddi.h, D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557575">DXGKARG_DESCRIBEALLOCATION</a>



<a href="https://msdn.microsoft.com/8ee65716-496c-4b0f-baa7-34a625847d5f">DxgkDdiDescribeAllocation</a>