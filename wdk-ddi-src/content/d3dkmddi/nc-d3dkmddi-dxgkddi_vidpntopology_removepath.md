---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH
title: DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH
author: windows-driver-content
description: The pfnRemovePath function removes a video present path to a specified VidPN topology object.
old-location: display\dxgk_vidpntopology_interface_pfnremovepath.htm
old-project: display
ms.assetid: 463973e0-c443-417a-86ff-0b78773d40cc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_vidpntopology_interface_pfnremovepath, pfnRemovePath callback function [Display Devices], pfnRemovePath, DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH, DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH, d3dkmddi/pfnRemovePath, VidPnFunctions_0a43b9cf-d4c2-4d6f-acc7-7988038c56e5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	pfnRemovePath
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH callback function
The <b>pfnRemovePath</b> function removes a video present path to a specified VidPN topology object.

## Syntax

```
DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH DxgkddiVidpntopologyRemovepath;

NTSTATUS DxgkddiVidpntopologyRemovepath(
  IN_CONST_D3DKMDT_HVIDPNTOPOLOGY hVidPnTopology,
  IN_CONST_D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId,
  IN_CONST_D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId
)
{...}
```

## Parameters

`hVidPnTopology`

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.

`VidPnSourceId`

[in] An integer that identifies a VidPN source path.

`VidPnTargetId`

[in] An integer that identifies a VidPN target path.


## Return Value

The <b>pfnRemovePath</b> function returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The specified video present path has been successfully removed from this VidPN topology object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>
</td>
<td width="60%">
The VidPN source identifier supplied in <i>VidPnSourceId </i>is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET</b></dt>
</dl>
</td>
<td width="60%">
The VidPN target identifier supplied in <i>VidPnTargetId </i>is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTopology </i>is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The path cannot be removed in the context of the current DDI call.

</td>
</tr>
</table>

## Remarks

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in<i> D3dkmdt.h</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |