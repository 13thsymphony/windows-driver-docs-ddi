---
UID : NC:d3dumddi.PFND3DDDI_SETVERTEXSHADERFUNC
title : PFND3DDDI_SETVERTEXSHADERFUNC
author : windows-driver-content
description : The SetVertexShaderFunc function sets the vertex shader code so that all of the subsequent drawing operations use that code.
old-location : display\setvertexshaderfunc.htm
old-project : display
ms.assetid : 2cea4812-7eba-4558-9c2e-30de460be21f
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.setvertexshaderfunc, SetVertexShaderFunc callback function [Display Devices], SetVertexShaderFunc, PFND3DDDI_SETVERTEXSHADERFUNC, PFND3DDDI_SETVERTEXSHADERFUNC, d3dumddi/SetVertexShaderFunc, UserModeDisplayDriver_Functions_aeaa5094-5619-4cf5-b2c3-c4b6aeed9b33.xml
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


# PFND3DDDI_SETVERTEXSHADERFUNC callback function
The <i>SetVertexShaderFunc</i> function sets the vertex shader code so that all of the subsequent drawing operations use that code.

## Syntax

```
PFND3DDDI_SETVERTEXSHADERFUNC Pfnd3dddiSetvertexshaderfunc;

HRESULT Pfnd3dddiSetvertexshaderfunc(
  HANDLE hDevice,
   HANDLE
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`HANDLE`




## Return Value

<i>SetVertexShaderFunc</i> returns S_OK or an appropriate error result if the vertex shader code is not successfully set.

## Remarks

After setting the vertex shader code, all of the drawing operations use that code until another code is selected.

For user-mode display drivers that support vertex shaders before version 2.0, the Microsoft Direct3D runtime passes 0 in the <i>hShaderHandle</i> parameter to indicate a fixed-function pipeline. For user-mode display drivers that support vertex shader version 2.0 or later, the runtime converts Direct3D fixed-function vertex state to vertex shader version 2.0. For more information fixed-function state, see <a href="https://msdn.microsoft.com/bc93d65e-ac16-470d-8c52-db8b1cc74456">Converting the Direct3D Fixed-Function State</a>.

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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETVERTEXSHADERFUNC callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>