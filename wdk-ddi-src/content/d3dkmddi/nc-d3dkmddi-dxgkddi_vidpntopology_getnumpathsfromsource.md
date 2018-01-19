---
UID : NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE
title : DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE
author : windows-driver-content
description : The pfnGetNumPathsFromSource function returns the number of video present paths that contain a specified video present source.
old-location : display\dxgk_vidpntopology_interface_pfngetnumpathsfromsource.htm
old-project : display
ms.assetid : 6c5ee84d-e106-47fc-88bd-b184e9cdd561
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dkmddi.h
req.include-header : D3dkmddi.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : pfnGetNumPathsFromSource
req.alt-loc : d3dkmddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE callback function
The <b>pfnGetNumPathsFromSource</b> function returns the number of video present paths that contain a specified video present source.

## Syntax

```
DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE DxgkddiVidpntopologyGetnumpathsfromsource;

NTSTATUS DxgkddiVidpntopologyGetnumpathsfromsource(
  IN_CONST_D3DKMDT_HVIDPNTOPOLOGY hVidPnTopology,
  IN_CONST_D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId,
  OUT_PSIZE_T pNumPathsFromSource
)
{...}
```

## Parameters

`hVidPnTopology`

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.

`VidPnSourceId`

[in] An integer that identifies a particular video present source.

`pNumPathsFromSource`

[out] A pointer to a SIZE_T-typed variable that receives the number of paths that contain the specified source.


## Return Value

The <b>pfnGetNumPathsFromSource</b> function returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>The handle supplied in <i>hVidPnTopology </i>was invalid.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The pointer supplied in <i>pNumPathsFromSource</i> was in valid.

## Remarks

A topology is a collection paths, each of which contains a (source, target) pair. It is possible for a particular source to appear in more than one path. For example, one source can be paired with two distinct targets in the case of a clone view.

VidPN source identifiers are assigned by the operating system. <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.

The D3DDDI_VIDEO_PRESENT_SOURCE_ID data type is defined in <i>D3dukmdt.h</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_getnumpaths.md">pfnGetNumPaths</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>