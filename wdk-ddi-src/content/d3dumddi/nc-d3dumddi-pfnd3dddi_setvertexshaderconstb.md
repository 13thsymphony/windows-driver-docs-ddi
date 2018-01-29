---
UID : NC:d3dumddi.PFND3DDDI_SETVERTEXSHADERCONSTB
title : PFND3DDDI_SETVERTEXSHADERCONSTB
author : windows-driver-content
description : The SetVertexShaderConstB function sets one or more vertex shader constant registers with Boolean values.
old-location : display\setvertexshaderconstb.htm
old-project : display
ms.assetid : 41ca823e-4370-4cba-9129-067e25a43a69
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.setvertexshaderconstb, SetVertexShaderConstB callback function [Display Devices], SetVertexShaderConstB, PFND3DDDI_SETVERTEXSHADERCONSTB, PFND3DDDI_SETVERTEXSHADERCONSTB, d3dumddi/SetVertexShaderConstB, UserModeDisplayDriver_Functions_5151bd4a-84a4-43d3-a76e-de6f5808281d.xml
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
req.typenames : DXGK_PTE
---


# PFND3DDDI_SETVERTEXSHADERCONSTB callback function
The <i>SetVertexShaderConstB</i> function sets one or more vertex shader constant registers with Boolean values.

## Syntax

```
PFND3DDDI_SETVERTEXSHADERCONSTB Pfnd3dddiSetvertexshaderconstb;

HRESULT Pfnd3dddiSetvertexshaderconstb(
  HANDLE hDevice,
  CONST D3DDDIARG_SETVERTEXSHADERCONSTB *,
  CONST BOOL *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`



`*`




## Return Value

<i>SetVertexShaderConstB</i> returns S_OK or an appropriate error result if the vertex shader constant registers are not successfully set with Boolean values.


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

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setvertexshaderconst.md">D3DDDIARG_SETVERTEXSHADERCONST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETVERTEXSHADERCONSTB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>