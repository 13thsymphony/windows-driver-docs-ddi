---
UID : NC:d3d10umddi.PFND3D10_2DDI_GETCAPS
title : PFND3D10_2DDI_GETCAPS
author : windows-driver-content
description : The GetCaps(D3D10_2) function queries for capabilities of the graphics adapter.
old-location : display\getcaps_d3d10_2_.htm
old-project : display
ms.assetid : 83cd5f34-5f12-4ead-ad33-366fc3c6e804
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : GetCaps(D3D10_2) is supported beginning with the Windows 7 operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : GetCaps
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


# PFND3D10_2DDI_GETCAPS callback function
The <i>GetCaps(D3D10_2)</i> function queries for capabilities of the graphics adapter.

## Syntax

```
PFND3D10_2DDI_GETCAPS Pfnd3d102DdiGetcaps;

HRESULT Pfnd3d102DdiGetcaps(
   D3D10DDI_HADAPTER,
  CONST D3D10_2DDIARG_GETCAPS *
)
{...}
```

## Parameters

`D3D10DDI_HADAPTER`



`*`




## Return Value

<i>GetCaps(D3D10_2)</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The capabilities are successfully retrieved.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>GetCaps(D3D10_2)</i> could not allocate memory that is required for it to complete.

## Remarks

The data that is returned by the <i>GetCaps(D3D10_2)</i> function in the <b>pData</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_2ddiarg_getcaps.md">D3D10_2DDIARG_GETCAPS</a> structure depends on the type of data that is requested (that is, the data depends on the <b>Type</b> member of D3D10_2DDIARG_GETCAPS and sometimes on the <b>pInfo</b> member).

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
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_2ddi_adapterfuncs.md">D3D10_2DDI_ADAPTERFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_2ddiarg_getcaps.md">D3D10_2DDIARG_GETCAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10_2DDI_GETCAPS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>