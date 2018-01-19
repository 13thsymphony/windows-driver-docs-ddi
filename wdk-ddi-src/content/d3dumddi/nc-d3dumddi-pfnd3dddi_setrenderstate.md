---
UID : NC:d3dumddi.PFND3DDDI_SETRENDERSTATE
title : PFND3DDDI_SETRENDERSTATE
author : windows-driver-content
description : The SetRenderState function updates a render state.
old-location : display\setrenderstate.htm
old-project : display
ms.assetid : 22fb67f7-cc28-4f10-950d-1379769ddf89
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_PTE, DXGK_PTE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SetRenderState
req.alt-loc : d3dumddi.h
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
req.typenames : DXGK_PTE
---


# PFND3DDDI_SETRENDERSTATE callback function
The <i>SetRenderState</i> function updates a render state.

## Syntax

```
PFND3DDDI_SETRENDERSTATE Pfnd3dddiSetrenderstate;

HRESULT Pfnd3dddiSetrenderstate(
  HANDLE hDevice,
  CONST D3DDDIARG_RENDERSTATE *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>SetRenderState</i> returns S_OK or an appropriate error result if the render state is not successfully updated.

## Remarks

The Microsoft Direct3D runtime maps <b>BeginScene</b> and <b>EndScene</b> calls from applications to the user-mode display driver's <i>SetRenderState</i> function. When the runtime receives a <b>BeginScene</b> call, it sets the <b>State</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_renderstate.md">D3DDDIARG_RENDERSTATE</a> structure that is pointed to by <i>pData</i> to D3DRENDERSTATE_SCENECAPTURE and the <b>Value</b> member of D3DDDIARG_RENDERSTATE to <b>TRUE</b> and then calls <i>SetRenderState</i>. When the runtime receives an <b>EndScene</b> call, it sets the <b>State</b> member to D3DRENDERSTATE_SCENECAPTURE and the <b>Value</b> member to <b>FALSE</b> and then calls <i>SetRenderState</i>. In between these calls to <i>SetRenderState</i>, the driver captures geometric data within a frame.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_renderstate.md">D3DDDIARG_RENDERSTATE</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETRENDERSTATE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>