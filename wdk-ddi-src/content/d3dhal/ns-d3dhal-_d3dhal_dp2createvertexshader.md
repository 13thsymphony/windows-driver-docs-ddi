---
UID : NS:d3dhal._D3DHAL_DP2CREATEVERTEXSHADER
title : _D3DHAL_DP2CREATEVERTEXSHADER
author : windows-driver-content
description : DirectX 8.0 and later versions only. The D3DHAL_DP2CRED3dDrawPrimitives2ATEVERTEXSHADER structure is used to create a vertex shader when a D3DDP2OP_CREATEVERTEXSHADER opcode is received by .
old-location : display\d3dhal_dp2createvertexshader.htm
old-project : display
ms.assetid : 41bea2bd-2b4d-467f-bb47-19b0b9f7ff6b
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DHAL_DP2CREATEVERTEXSHADER, D3DHAL_DP2CREATEVERTEXSHADER, *LPD3DHAL_DP2CREATEVERTEXSHADER
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
req.alt-api : D3DHAL_DP2CREATEVERTEXSHADER
req.alt-loc : d3dhal.h
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
req.typenames : D3DHAL_DP2CREATEVERTEXSHADER
---

# _D3DHAL_DP2CREATEVERTEXSHADER structure
DirectX 8.0 and later versions only.
   

The D3DHAL_DP2CRE<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>ATEVERTEXSHADER structure is used to create a vertex shader when a D3DDP2OP_CREATEVERTEXSHADER opcode is received by .

## Syntax
````
typedef struct _D3DHAL_DP2CREATEVERTEXSHADER {
  DWORD dwHandle;
  DWORD dwDeclSize;
  DWORD dwCodeSize;
} D3DHAL_DP2CREATEVERTEXSHADER, *LPD3DHAL_DP2CREATEVERTEXSHADER;
````

## Members

        
            `dwCodeSize`

            Specifies the shader code size in bytes.
        
            `dwDeclSize`

            Specifies the shader declaration size in bytes.
        
            `dwHandle`

            Specifies the handle to the vertex shader that is assigned by the runtime. This value is guaranteed to be subzero. Furthermore, although flexible vertex format (FVF) codes are part of the shader handle namespace, it is guaranteed that the handle passed will not be an FVF code.

    ## Remarks
        Before invoking the driver, the runtime performs validation to ensure that the specified shader is legal for the specified shader language version. The runtime flushes all pending state and rendering when this token is to be sent to the driver. Thus, processing of this token is assumed to be synchronous with the runtime and the driver reports failure of the creation request by failing the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> DDI call. Thus, the driver should validate the given shader declaration and code on receipt of this token and report success or failure accordingly. 

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff552855">Direct3D Driver Shader Codes</a> for information about the format of an individual shader code and the tokens that comprise each shader code.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dhal.h (include D3dhal.h) |

    ## See Also

        <dl>
<dt>D3DDP2OP_CREATEVERTEXSHADER</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2vertexshader.md">D3DHAL_DP2VERTEXSHADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2CREATEVERTEXSHADER structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>