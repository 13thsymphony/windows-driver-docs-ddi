---
UID: NS:d3dhal._D3DHAL_DP2CREATEVERTEXSHADERFUNC
title: "_D3DHAL_DP2CREATEVERTEXSHADERFUNC"
author: windows-driver-content
description: DirectX 9.0 and later versions only. The D3DHAL_DP2CREATEVERTEXSHADERFUNC structure is used to create a vertex shader code object when a D3DDP2OP_CREATEVERTEXSHADERFUNC opcode is received by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2createvertexshaderfunc.htm
old-project: display
ms.assetid: 2b7456e5-a6fa-42bf-aace-21d555c3e821
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DHAL_DP2CREATEVERTEXSHADERFUNC, d3dhal/LPD3DHAL_DP2CREATEVERTEXSHADERFUNC, d3dhal/D3DHAL_DP2CREATEVERTEXSHADERFUNC, D3DHAL_DP2CREATEVERTEXSHADERFUNC structure [Display Devices], display.d3dhal_dp2createvertexshaderfunc, LPD3DHAL_DP2CREATEVERTEXSHADERFUNC, d3dstrct_cb83183c-18cc-4e11-814f-2b50836cbe39.xml, *LPD3DHAL_DP2CREATEVERTEXSHADERFUNC, LPD3DHAL_DP2CREATEVERTEXSHADERFUNC structure pointer [Display Devices], D3DHAL_DP2CREATEVERTEXSHADERFUNC"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dhal.h
apiname:
-	D3DHAL_DP2CREATEVERTEXSHADERFUNC
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2CREATEVERTEXSHADERFUNC
---

# _D3DHAL_DP2CREATEVERTEXSHADERFUNC structure
DirectX 9.0 and later versions only.
   

The D3DHAL_DP2CREATEVERTEXSHADERFUNC structure is used to create a vertex shader code object when a D3DDP2OP_CREATEVERTEXSHADERFUNC opcode is received by <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.

## Syntax
````
typedef struct _D3DHAL_DP2CREATEVERTEXSHADERFUNC {
  DWORD dwHandle;
  DWORD dwSize;
} D3DHAL_DP2CREATEVERTEXSHADERFUNC, *LPD3DHAL_DP2CREATEVERTEXSHADERFUNC;
````

## Members


`dwHandle`

Specifies the handle to the vertex shader code that is assigned by the runtime. This value is guaranteed to be subzero.

`dwSize`

Specifies the shader code size in bytes.

## Remarks
When the runtime calls the driver's <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> function with this token, the driver should validate the given shader code and report success or failure accordingly. 

Vertex shader code follows D3DHAL_DP2CREATEVERTEXSHADERFUNC in the command stream. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff552855">Direct3D Driver Shader Codes</a> for information about the format of individual shader code and the tokens that comprise each shader code. 

The DirectX 9.0 runtime sets <b>dwHandle</b> to zero to indicate a fixed function pipeline.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2createvertexshaderdecl.md">D3DHAL_DP2CREATEVERTEXSHADERDECL</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2vertexshader.md">D3DHAL_DP2VERTEXSHADER</a>



D3DDP2OP_CREATEVERTEXSHADERFUNC



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2CREATEVERTEXSHADERFUNC structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>