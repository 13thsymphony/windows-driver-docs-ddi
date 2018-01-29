---
UID : NS:d3dhal._D3DHAL_DP2CREATEVERTEXSHADERDECL
title : _D3DHAL_DP2CREATEVERTEXSHADERDECL
author : windows-driver-content
description : DirectX 9.0 and later versions only. The D3DHAL_DP2CREATEVERTEXSHADERDECL structure is used to create a vertex shader declaration when a D3DDP2OP_CREATEVERTEXSHADERDECL opcode is received by D3dDrawPrimitives2.
old-location : display\d3dhal_dp2createvertexshaderdecl.htm
old-project : display
ms.assetid : 063e72ef-7d57-484a-98f8-b6166a238096
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : LPD3DHAL_DP2CREATEVERTEXSHADERDECL structure pointer [Display Devices], LPD3DHAL_DP2CREATEVERTEXSHADERDECL, d3dhal/LPD3DHAL_DP2CREATEVERTEXSHADERDECL, d3dhal/D3DHAL_DP2CREATEVERTEXSHADERDECL, display.d3dhal_dp2createvertexshaderdecl, d3dstrct_ae2ef7ce-67b3-4c91-b4d8-e3ff8b82734b.xml, _D3DHAL_DP2CREATEVERTEXSHADERDECL, *LPD3DHAL_DP2CREATEVERTEXSHADERDECL, D3DHAL_DP2CREATEVERTEXSHADERDECL, D3DHAL_DP2CREATEVERTEXSHADERDECL structure [Display Devices]
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
req.typenames : D3DHAL_DP2CREATEVERTEXSHADERDECL
---

# _D3DHAL_DP2CREATEVERTEXSHADERDECL structure
DirectX 9.0 and later versions only.
   

The D3DHAL_DP2CREATEVERTEXSHADERDECL structure is used to create a vertex shader declaration when a D3DDP2OP_CREATEVERTEXSHADERDECL opcode is received by <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.

## Syntax
````
typedef struct _D3DHAL_DP2CREATEVERTEXSHADERDECL {
  DWORD dwHandle;
  DWORD dwNumVertexElements;
} D3DHAL_DP2CREATEVERTEXSHADERDECL, *LPD3DHAL_DP2CREATEVERTEXSHADERDECL;
````

## Members


`dwHandle`

Specifies the handle to the vertex shader declaration that is assigned by the runtime. This value is guaranteed to be subzero. Flexible vertex format (FVF) codes are part of the shader declaration handle namespace. If bit zero of the handle is set, the handle passed is a shader declaration handle; otherwise, an FVF code.

`dwNumVertexElements`

Specifies the number of vertex elements that make up the shader declaration.

## Remarks
When the runtime calls the driver's <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> function with this token, the driver should validate the given shader declaration and report success or failure accordingly. 

An array of D3DVERTEXELEMENT9 structures that define the vertex elements that make up the shader declaration follow D3DHAL_DP2CREATEVERTEXSHADERDECL in the command stream. For more information about D3DVERTEXELEMENT9, see the latest DirectX SDK documentation.

The DirectX 9.0 runtime specifies a legacy FVF code or a declaration handle in the <b>dwHandle</b> member. The runtime indicates a declaration handle by setting bit 0 of the handle.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

D3DDP2OP_CREATEVERTEXSHADERDECL

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2vertexshader.md">D3DHAL_DP2VERTEXSHADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2CREATEVERTEXSHADERDECL structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>