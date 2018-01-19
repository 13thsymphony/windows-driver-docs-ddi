---
UID : NC:d3d10umddi.PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE
title : PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE
author : windows-driver-content
description : The CalcPrivateDeferredContextSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a deferred context.
old-location : display\calcprivatedeferredcontextsize.htm
old-project : display
ms.assetid : 282898b1-45e1-4d85-9ab7-fd400623bdc5
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : CalcPrivateDeferredContextSize is supported beginning with the Windows 7 operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : CalcPrivateDeferredContextSize
req.alt-loc : d3d10umddi.h
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
req.typenames : "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE callback function
The <b>CalcPrivateDeferredContextSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a deferred context.

## Syntax

```
PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE Pfnd3d11ddiCalcprivatedeferredcontextsize;

SIZE_T Pfnd3d11ddiCalcprivatedeferredcontextsize(
   D3D10DDI_HDEVICE,
  CONST D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

<b>CalcPrivateDeferredContextSize</b> returns the size of the memory region that the driver requires to create a deferred context.

## Remarks

The driver is only required to implement <b>CalcPrivateDeferredContextSize</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_calcprivatedeferredcontextsize.md">D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>