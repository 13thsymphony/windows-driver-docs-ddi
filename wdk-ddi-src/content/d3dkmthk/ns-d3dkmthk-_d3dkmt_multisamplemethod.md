---
UID: NS:d3dkmthk._D3DKMT_MULTISAMPLEMETHOD
title: "_D3DKMT_MULTISAMPLEMETHOD"
author: windows-driver-content
description: The D3DKMT_MULTISAMPLEMETHOD structure describes a multiple-sampling method.
old-location: display\d3dkmt_multisamplemethod.htm
old-project: display
ms.assetid: 6cdc0665-61e6-4c13-9b15-46ce301febec
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_MULTISAMPLEMETHOD, D3DKMT_MULTISAMPLEMETHOD structure [Display Devices], OpenGL_Structs_0617065f-aa53-4b1a-9a3f-e135972d4852.xml, _D3DKMT_MULTISAMPLEMETHOD, d3dkmthk/D3DKMT_MULTISAMPLEMETHOD, display.d3dkmt_multisamplemethod
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_MULTISAMPLEMETHOD
product: Windows
targetos: Windows
req.typenames: D3DKMT_MULTISAMPLEMETHOD
---

# _D3DKMT_MULTISAMPLEMETHOD structure
The D3DKMT_MULTISAMPLEMETHOD structure describes a multiple-sampling method.

## Syntax
````
typedef struct _D3DKMT_MULTISAMPLEMETHOD {
  UINT NumSamples;
  UINT NumQualityLevels;
  UINT Reserved;
} D3DKMT_MULTISAMPLEMETHOD;
````

## Members


`NumSamples`

[out] The number of subpixels that are used in the multiple-sampling method (for example, 2 for 2x and 8 for 8x multiple-sampling).

`NumQualityLevels`

[out] The upper bound on the quality range that is supported for the multiple-sampling method. The range extends from zero through the reported maximum quality setting.

`Reserved`

[out] Reserved.

## Remarks
The driver can partition its quality levels for a given multiple-sampling method into as many increments as it requires, with the condition that each incremental step noticeably improves the quality of the presented image.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetmultisamplemethodlist.md">D3DKMTGetMultisampleMethodList</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getmultisamplemethodlist.md">D3DKMT_GETMULTISAMPLEMETHODLIST</a>