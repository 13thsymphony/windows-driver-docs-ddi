---
UID : NS:d3d10umddi.D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW
title : D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW
author : windows-driver-content
description : The D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure describes a buffer that is used to create a shader resource view in a call to the CreateShaderResourceView function.
old-location : display\d3d10ddiarg_buffer_shaderresourceview.htm
old-project : display
ms.assetid : 9144b167-7fa4-4854-bf0c-e98192f07db8
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : UMDisplayDriver_Dx10param_Structs_76ff32e8-1460-45a7-a63d-3c18b75a860e.xml, D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure [Display Devices], display.d3d10ddiarg_buffer_shaderresourceview, d3d10umddi/D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW, D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
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
req.typenames : D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW
---

# D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure
The D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure describes a buffer that is used to create a shader resource view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview.md">CreateShaderResourceView</a> function.

## Syntax
````
typedef struct D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW {
  union {
    UINT FirstElement;
    UINT ElementOffset;
  };
  union {
    UINT NumElements;
    UINT ElementWidth;
  };
} D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview.md">CreateShaderResourceView</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createshaderresourceview.md">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>