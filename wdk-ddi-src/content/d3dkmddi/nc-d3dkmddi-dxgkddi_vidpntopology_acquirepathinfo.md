---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO
author: windows-driver-content
description: The pfnAcquirePathInfo function returns a descriptor of the video present path specified by a video present source and a video present target within a particular VidPN topology.
old-location: display\dxgk_vidpntopology_interface_pfnacquirepathinfo.htm
old-project: display
ms.assetid: 27a03106-a5b5-489c-968a-81b3ea9940cb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_vidpntopology_interface_pfnacquirepathinfo, pfnAcquirePathInfo callback function [Display Devices], pfnAcquirePathInfo, DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO, DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO, d3dkmddi/pfnAcquirePathInfo, VidPnFunctions_fb690a8a-fc98-4f8f-bfe5-14168a5fdb6a.xml
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
-	pfnAcquirePathInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO callback function
The <b>pfnAcquirePathInfo</b> function returns a descriptor of the video present path specified by a video present source and a video present target within a particular VidPN topology.

## Syntax

```
DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO DxgkddiVidpntopologyAcquirepathinfo;

NTSTATUS DxgkddiVidpntopologyAcquirepathinfo(
  IN_CONST_D3DKMDT_HVIDPNTOPOLOGY hVidPnTopology,
  IN_CONST_D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId,
  IN_CONST_D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId,
  DEREF_OUT_CONST_PPD3DKMDT_VIDPN_PRESENT_PATH ppVidPnPresentPathInfo
)
{...}
```

## Parameters

`hVidPnTopology`

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.

`VidPnSourceId`

[in] An integer that identifies a video present source.

`VidPnTargetId`

[in] An integer that identifies a video present target.

`ppVidPnPresentPathInfo`




## Return Value

The <b>pfnAcquirePathInfo</b> function returns one of the following values:

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
</table>

## Remarks

When you have finished using the D3DKMDT_VIDPN_PRESENT_PATH structure, you must release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo.md">pfnReleasePathInfo</a>.

A path contains a (source, target) pair, and a topology is a collection of paths. This function returns a descriptor for the path, in a specified topology, that contains a specified (source, target) pair.

You can enumerate all the paths that belong to a VidPN topology object by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo.md">pfnAcquireFirstPathInfo</a> and then making a sequence of calls to <b>pfnAcquireNextPathInfo</b>.

VidPN source identifiers are assigned by the operating system. <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

VidPN target identifiers are assigned by the display miniport driver. <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.

The D3DDDI_VIDEO_PRESENT_SOURCE_ID and D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in <i>D3dukmdt.h</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo.md">pfnReleasePathInfo</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo.md">pfnAcquireFirstPathInfo</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirenextpathinfo.md">pfnAcquireNextPathInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>