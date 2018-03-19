---
UID: NS:d3dumddi._DXVADDI_DECODEBUFFERINFO
title: "_DXVADDI_DECODEBUFFERINFO"
author: windows-driver-content
description: The DXVADDI_DECODEBUFFERINFO structure describes information about a particular type of compressed buffer that is required for a video decoding scenario.
old-location: display\dxvaddi_decodebufferinfo.htm
old-project: display
ms.assetid: e0a0ad31-86c1-44bd-b069-70442973a539
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVA2_Structs_b076dffc-bfe0-4141-a075-9349b69af16c.xml, DXVADDI_DECODEBUFFERINFO, DXVADDI_DECODEBUFFERINFO structure [Display Devices], _DXVADDI_DECODEBUFFERINFO, d3dumddi/DXVADDI_DECODEBUFFERINFO, display.dxvaddi_decodebufferinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	DXVADDI_DECODEBUFFERINFO
product: Windows
targetos: Windows
req.typenames: DXVADDI_DECODEBUFFERINFO
---

# _DXVADDI_DECODEBUFFERINFO structure
The DXVADDI_DECODEBUFFERINFO structure describes information about a particular type of compressed buffer that is required for a video decoding scenario.

## Syntax
````
typedef struct _DXVADDI_DECODEBUFFERINFO {
  D3DDDIFORMAT CompressedBufferType;
  UINT         CreationWidth;
  UINT         CreationHeight;
  D3DDDI_POOL  CreationPool;
} DXVADDI_DECODEBUFFERINFO;
````

## Members


`CompressedBufferType`

[out] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the buffer.

`CreationWidth`

[out] The width of the data in the buffer as the number of units of bits. For example, AYUV data is specified in 32-bit units, IA44/AI44 data is specified in 8-bit units, and DPXD data is specified in 2-bit units.

The driver must assign a value to <b>CreationWidth</b> that is a multiple of 2 and does not exceed 65535.

`CreationHeight`

[out] The height of the data in the buffer as the number of units of bits. For example, AYUV data is specified in 32-bit units, IA44/AI44 data is specified in 8-bit units, and DPXD data is specified in 2-bit units.

The driver must assign a value to <b>CreationHeight</b> that does not exceed 65535.

`CreationPool`

[out] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_pool.md">D3DDDI_POOL</a>-typed value that indicates the type of memory that the buffer exists in.

## Remarks
A pointer to the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodeinput.md">DXVADDI_DECODEINPUT</a> structure is specified in the <b>pInfo</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> structure--along with a D3DDDICAPS_GETDECODECOMPRESSEDBUFFERINFO value in the <b>Type</b> member of D3DDDIARG_GETCAPS--in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function to retrieve information about the types of compressed buffers that are required to accelerate a particular DirectX VA video decode type. The information about the types of compressed buffers is returned in an array of DXVADDI_DECODEBUFFERINFO structures through the <b>pData</b> member of D3DDDIARG_GETCAPS.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodeinput.md">DXVADDI_DECODEINPUT</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>