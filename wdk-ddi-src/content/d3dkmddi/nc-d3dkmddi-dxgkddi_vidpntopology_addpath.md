---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ADDPATH
title: DXGKDDI_VIDPNTOPOLOGY_ADDPATH
author: windows-driver-content
description: The pfnAddPath function adds a video present path to a specified VidPN topology object.
old-location: display\dxgk_vidpntopology_interface_pfnaddpath.htm
old-project: display
ms.assetid: 893e0be1-aa29-429a-a3ca-a9f19053fd92
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_ADDPATH, VidPnFunctions_9c594989-a5f6-4977-8a1b-0302d30e8df7.xml, d3dkmddi/pfnAddPath, display.dxgk_vidpntopology_interface_pfnaddpath, pfnAddPath, pfnAddPath callback function [Display Devices]
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnAddPath
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_VIDPNTOPOLOGY_ADDPATH callback function
The <b>pfnAddPath</b> function adds a video present path to a specified VidPN topology object.

## Syntax

```
DXGKDDI_VIDPNTOPOLOGY_ADDPATH DxgkddiVidpntopologyAddpath;

NTSTATUS DxgkddiVidpntopologyAddpath(
  IN_D3DKMDT_HVIDPNTOPOLOGY hVidPnTopology,
  IN_PD3DKMDT_VIDPN_PRESENT_PATH pVidPnPresentPath
)
{...}
```

## Parameters

`hVidPnTopology`

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.

`pVidPnPresentPath`

[in] A pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure that describes the path. The display miniport driver previously obtained this pointer by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_createnewpathinfo.md">pfnCreateNewPathInfo</a>.


## Return Value

The <b>pfnAddPath</b> function returns one of the following values:

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
The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTopology </i>was invalid.

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

To add a path to a topology, the display miniport driver performs the following steps.

Call <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_createnewpathinfo.md">pfnCreateNewPathInfo</a> to obtain a pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure allocated by the VidPN manager.

Populate the D3DKMDT_VIDPN_PRESENT_PATH structure with information about the path, including video present source and target identifiers.

Call <b>pfnAddPath</b> to add the path to a topology. 

The VidPN manager allocates a D3DKMDT_VIDPN_PRESENT_PATH structure when you call <b>pfnCreateNewPathInfo</b>. If you add the path described by that structure to a topology, then you do not need to explicitly release the structure; <b>pfnAddPath</b> releases it.

If you obtain a D3DKMDT_VIDPN_PRESENT_PATH structure by calling <b>pfnCreateNewPathInfo</b> and then decide not to add that path to a topology, then you must explicity release the structure by calling <b>pfnReleasePathInfo</b>.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in<i> D3dkmdt.h</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo.md">pfnReleasePathInfo</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_createnewpathinfo.md">pfnCreateNewPathInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTOPOLOGY_ADDPATH callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>