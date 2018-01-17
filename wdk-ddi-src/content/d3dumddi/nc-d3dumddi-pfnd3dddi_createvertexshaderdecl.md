---
UID: NC:d3dumddi.PFND3DDDI_CREATEVERTEXSHADERDECL
title: PFND3DDDI_CREATEVERTEXSHADERDECL
author: windows-driver-content
description: The CreateVertexShaderDecl function converts the vertex shader declaration into a hardware-specific format and associates the declaration with a shader handle.
old-location: display\createvertexshaderdecl.htm
old-project: display
ms.assetid: 00c53e81-93db-46b8-b65c-c8d62059452a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateVertexShaderDecl
req.alt-loc: d3dumddi.h
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
req.typenames: *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
---

# PFND3DDDI_CREATEVERTEXSHADERDECL callback



## -description
The <b>CreateVertexShaderDecl</b> function converts the vertex shader declaration into a hardware-specific format and associates the declaration with a shader handle.



## -prototype

````
PFND3DDDI_CREATEVERTEXSHADERDECL CreateVertexShaderDecl;

__checkReturn HRESULT APIENTRY CreateVertexShaderDecl(
  _In_          HANDLE                           hDevice,
  _Inout_       D3DDDIARG_CREATEVERTEXSHADERDECL *pData,
  _In_    const D3DDDIVERTEXELEMENT              *pVertexElements
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createvertexshaderdecl.md">D3DDDIARG_CREATEVERTEXSHADERDECL</a> structure that retrieves the shader handle that is associated with the vertex shader declaration that is specified by <i>pVertexElements</i>.


### -param pVertexElements [in]

 An array of <a href="..\d3dumddi\ns-d3dumddi-_d3dddivertexelement.md">D3DDDIVERTEXELEMENT</a> structures that make up the vertex shader declaration.


## -returns
<b>CreateVertexShaderDecl</b> returns S_OK or an appropriate error result if the vertex shader declaration object is not successfully created.


## -remarks
The array of D3DDDIVERTEXELEMENT structures specified by <i>pVertexElements</i> defines vertex data into the pipeline. 

For more information about programming shader assemblers, see <a href="https://msdn.microsoft.com/c858766c-b414-4971-b4d9-23ec94aca8ea">Processing Shader Codes</a>.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createvertexshaderdecl.md">D3DDDIARG_CREATEVERTEXSHADERDECL</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddivertexelement.md">D3DDDIVERTEXELEMENT</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CREATEVERTEXSHADERDECL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

