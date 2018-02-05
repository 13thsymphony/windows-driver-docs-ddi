---
UID : NS:d3dhal._D3DHAL_DP2EXT
title : "_D3DHAL_DP2EXT"
author : windows-driver-content
description : The D3DHAL_DP2EXT structure's use has yet to be defined.
old-location : display\d3dhal_dp2ext.htm
old-project : display
ms.assetid : d7cec277-d1d3-4c0f-91ec-fd5e962b6e1c
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DHAL_DP2EXT, LPD3DHAL_DP2EXT structure pointer [Display Devices], LPD3DHAL_DP2EXT, D3DHAL_DP2EXT structure [Display Devices], d3dhal/LPD3DHAL_DP2EXT, *LPD3DHAL_DP2EXT, display.d3dhal_dp2ext, _D3DHAL_DP2EXT, d3dhal/D3DHAL_DP2EXT, d3dstrct_e56171cd-ae20-4277-abd5-cb8f0c008637.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dhal.h
req.include-header : D3dhal.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DHAL_DP2EXT
---

# _D3DHAL_DP2EXT structure
The D3DHAL_DP2EXT structure's use has yet to be defined.

## Syntax
````
typedef struct _D3DHAL_DP2EXT {
  DWORD dwExtToken;
  DWORD dwSize;
} D3DHAL_DP2EXT, *LPD3DHAL_DP2EXT;
````

## Members


`dwExtToken`

Specifies the extension token.

`dwSize`

Specifies the size, in bytes of this structure.

## Remarks
This structure is used with hardware transform and lighting. Contact the DirectX team at Microsoft for further implementation details.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dhal.h (include D3dhal.h) |