---
UID : NS:d3d10umddi.D3D10DDIARG_CREATEELEMENTLAYOUT
title : D3D10DDIARG_CREATEELEMENTLAYOUT
author : windows-driver-content
description : The D3D10DDIARG_CREATEELEMENTLAYOUT structure describes the element layout to create.
old-location : display\d3d10ddiarg_createelementlayout.htm
old-project : display
ms.assetid : 3eb1555b-3274-496d-b6af-9cb0a6083ee4
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D10DDIARG_CREATEELEMENTLAYOUT, D3D10DDIARG_CREATEELEMENTLAYOUT structure [Display Devices], UMDisplayDriver_Dx10param_Structs_8c912e61-9cff-46ad-963f-16d3b9a13b10.xml, d3d10umddi/D3D10DDIARG_CREATEELEMENTLAYOUT, display.d3d10ddiarg_createelementlayout
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
req.typenames : D3D10DDIARG_CREATEELEMENTLAYOUT
---

# D3D10DDIARG_CREATEELEMENTLAYOUT structure
The D3D10DDIARG_CREATEELEMENTLAYOUT structure describes the element layout to create.

## Syntax
````
typedef struct D3D10DDIARG_CREATEELEMENTLAYOUT {
  const D3D10DDIARG_INPUT_ELEMENT_DESC *pVertexElements;
  UINT                                 NumElements;
} D3D10DDIARG_CREATEELEMENTLAYOUT;
````

## Members


`NumElements`

[in] The number of elements in that array that the <b>pVertexElements</b> member specifies.

`pVertexElements`

[in] An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_input_element_desc.md">D3D10DDIARG_INPUT_ELEMENT_DESC</a> structures that describes each element in the element layout.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_input_element_desc.md">D3D10DDIARG_INPUT_ELEMENT_DESC</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateelementlayoutsize.md">CalcPrivateElementLayoutSize</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createelementlayout.md">CreateElementLayout</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_CREATEELEMENTLAYOUT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>