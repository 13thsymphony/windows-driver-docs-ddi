---
UID: NS:d3dhal._D3DHAL_DP2SETVERTEXSHADERCONST
title: "_D3DHAL_DP2SETVERTEXSHADERCONST"
author: windows-driver-content
description: DirectX 8.0 and later versions only. The D3DHAL_DP2SETVERTEXSHADERCONST structure is used to set one or more of the vertex shader constant registers when the D3DDP2OP_SETVERTEXSHADERCONST opcode is received by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setvertexshaderconst.htm
old-project: display
ms.assetid: f3973564-8739-4bf7-b9f7-e5792018b98d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3DHAL_DP2SETVERTEXSHADERCONSTB, *LPD3DHAL_DP2SETVERTEXSHADERCONST, D3DHAL_DP2SETVERTEXSHADERCONST structure [Display Devices], display.d3dhal_dp2setvertexshaderconst, d3dstrct_5d02ceb6-1d80-4586-a256-ca56ca51a101.xml, d3dhal/D3DHAL_DP2SETVERTEXSHADERCONST, LPD3DHAL_DP2SETVERTEXSHADERCONST, _D3DHAL_DP2SETVERTEXSHADERCONST, D3DHAL_DP2SETVERTEXSHADERCONST, D3DHAL_DP2SETVERTEXSHADERCONSTI, d3dhal/LPD3DHAL_DP2SETVERTEXSHADERCONST, LPD3DHAL_DP2SETVERTEXSHADERCONST structure pointer [Display Devices], *LPD3DHAL_DP2SETVERTEXSHADERCONSTI, *LPD3DHAL_DP2SETVERTEXSHADERCONSTB
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
-	D3DHAL_DP2SETVERTEXSHADERCONST
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETVERTEXSHADERCONST
---

# _D3DHAL_DP2SETVERTEXSHADERCONST structure
DirectX 8.0 and later versions only.
   

The D3DHAL_DP2SETVERTEXSHADERCONST structure is used to set one or more of the vertex shader constant registers when the D3DDP2OP_SETVERTEXSHADERCONST opcode is received by <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.

## Syntax
````
typedef struct _D3DHAL_DP2SETVERTEXSHADERCONST {
  DWORD dwRegister;
  DWORD dwCount;
} D3DHAL_DP2SETVERTEXSHADERCONST, *LPD3DHAL_DP2SETVERTEXSHADERCONST;
````

## Members


`dwCount`

Specifies the number of constant registers to set and, therefore, the number of four element, single precision float vectors to read from the DP2 stream.

`dwRegister`

Specifies the index of the first vertex shader constant to have its value sent.

## Remarks
A start register and register count are given. One or more vectors of four single precision floating-point values immediately follow the D3DHAL_DP2SETVERTEXSHADERCONST data structure in the DP2 stream.

The runtime validates that the range of registers specified is legal given the level of vertex shader support reported to the driver. Furthermore, if the driver does not support any form of programmable vertex processing the runtime does not send this token to the driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

D3DDP2OP_SETVERTEXSHADERCONST



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2createvertexshader.md">D3DHAL_DP2CREATEVERTEXSHADER</a>



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2vertexshader.md">D3DHAL_DP2VERTEXSHADER</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETVERTEXSHADERCONST structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>