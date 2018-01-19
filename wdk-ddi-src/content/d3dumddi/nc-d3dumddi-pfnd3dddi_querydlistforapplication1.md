---
UID : NC:d3dumddi.PFND3DDDI_QUERYDLISTFORAPPLICATION1
title : PFND3DDDI_QUERYDLISTFORAPPLICATION1
author : windows-driver-content
description : Called during Microsoft Direct3D initialization on a hybrid system to determine which GPU an application should run on. A dList is a list of applications that need cross-adapter shared surfaces for high-performance rendering on the discrete GPU.
old-location : display\querydlistforapplication1.htm
old-project : display
ms.assetid : 4F27E884-D21C-483D-9E53-02D405D02F10
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_PTE, DXGK_PTE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dumddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : QueryDListForApplication
req.alt-loc : D3dumddi.h
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


# PFND3DDDI_QUERYDLISTFORAPPLICATION1 callback function
Called during Microsoft Direct3D initialization on a <a href="display.using_cross-adapter_resources_in_a_hybrid_system#definition_of_a_hybrid_system#definition_of_a_hybrid_system">hybrid system</a> to determine which GPU an application should run on. A <i>dList</i> is a list of applications that need cross-adapter shared surfaces for high-performance rendering on the discrete GPU.

## Syntax

```
PFND3DDDI_QUERYDLISTFORAPPLICATION1 Pfnd3dddiQuerydlistforapplication1;

HRESULT Pfnd3dddiQuerydlistforapplication1(
  BOOL *,
   HANDLE,
   PFND3DDDI_ESCAPECB
)
{...}
```

## Parameters

`*`



`HANDLE`



`PFND3DDDI_ESCAPECB`




## Return Value

Returns <b>S_OK</b>, or an appropriate error result if the operation is not successful.

## Remarks

For more information on how to call this function and set up the DLL that exports it, see <a href="https://msdn.microsoft.com/8AABE677-2C2D-4CFD-AF22-06D65524A158">Hybrid system DDI</a>.

For more general information on hybrid systems, see <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">Using cross-adapter resources in a hybrid system</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3d10umddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_QUERYDLISTFORAPPLICATION1 callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>