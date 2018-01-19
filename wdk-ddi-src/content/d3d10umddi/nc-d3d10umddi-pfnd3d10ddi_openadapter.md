---
UID : NC:d3d10umddi.PFND3D10DDI_OPENADAPTER
title : PFND3D10DDI_OPENADAPTER
author : windows-driver-content
description : The OpenAdapter10 function creates a graphics adapter object that is referenced in subsequent calls.
old-location : display\openadapter10.htm
old-project : display
ms.assetid : 50c10021-2bad-4e3c-99cc-24cf31fbc95d
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : OpenAdapter10
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


# PFND3D10DDI_OPENADAPTER callback function
The <i>OpenAdapter10</i> function creates a graphics adapter object that is referenced in subsequent calls.

## Syntax

```
PFND3D10DDI_OPENADAPTER Pfnd3d10ddiOpenadapter;

HRESULT Pfnd3d10ddiOpenadapter(
  D3D10DDIARG_OPENADAPTER *
)
{...}
```

## Parameters

`*`




## Return Value

<i>OpenAdapter10</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The graphics adapter object was successfully created.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>OpenAdapter10</i> could not allocate memory that was required for it to complete.

## Remarks

The graphics adapter object that is created by the <i>OpenAdapter10</i> function represents the underlying graphics hardware. Before the Direct3D runtime can create a display device by calling <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>, the user-mode display driver should call the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a> function to query for the graphics hardware capabilities from the display miniport driver. 

The Direct3D runtime can open multiple graphics adapter objects from a single graphics adapter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_openadapter.md">D3D10DDIARG_OPENADAPTER</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_OPENADAPTER callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>