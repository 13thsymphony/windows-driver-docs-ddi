---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_RELEASESOURCEMODESET
title: DXGKDDI_VIDPN_RELEASESOURCEMODESET
author: windows-driver-content
description: The pfnReleaseSourceModeSet function releases a handle to a source mode set object.
old-location: display\dxgk_vidpn_interface_pfnreleasesourcemodeset.htm
old-project: display
ms.assetid: f1ee8761-f36e-4a39-a78e-95975442f7d3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgk_vidpn_interface_pfnreleasesourcemodeset, pfnReleaseSourceModeSet callback function [Display Devices], pfnReleaseSourceModeSet, DXGKDDI_VIDPN_RELEASESOURCEMODESET, DXGKDDI_VIDPN_RELEASESOURCEMODESET, d3dkmddi/pfnReleaseSourceModeSet, VidPnFunctions_601f59ab-13a9-4c65-8c94-6a7d962c01f9.xml
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
-	pfnReleaseSourceModeSet
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_VIDPN_RELEASESOURCEMODESET callback function
The <b>pfnReleaseSourceModeSet</b> function releases a handle to a source mode set object.

## Syntax

```
DXGKDDI_VIDPN_RELEASESOURCEMODESET DxgkddiVidpnReleasesourcemodeset;

NTSTATUS DxgkddiVidpnReleasesourcemodeset(
  IN_CONST_D3DKMDT_HVIDPN hVidPn,
  IN_CONST_D3DKMDT_HVIDPNSOURCEMODESET hVidPnSourceModeSet
)
{...}
```

## Parameters

`hVidPn`

[in] A handle to the VidPN object that contains the source mode set object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a>, or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a>.

`hVidPnSourceModeSet`

[in] The handle to be released.


## Return Value

The <b>pfnReleaseSourceModeSet</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPn</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnSourceModeSet</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_RESOURCES_NOT_RELATED</b></dt>
</dl>
</td>
<td width="60%">
The VidPN identified by <i>hVidPn</i> does not contain the source mode set identified by <i>hVidPnSourceModeSet</i>.

</td>
</tr>
</table>

## Remarks

When you have finished using a handle that you obtained by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md">pfnAcquireSourceModeSet</a>, you must release the handle by calling <b>pfnReleaseSourceModeSet</b>.

If you obtain a handle by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_createnewsourcemodeset.md">pfnCreateNewSourceModeSet</a> and then pass that handle to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_assignsourcemodeset.md">pfnAssignSourceModeSet</a>, you do not need to release the handle.

If you obtain a handle by calling <b>pfnCreateNewSourceModeSet</b> and then you decide not to assign the new source mode set to a source, you must release the newly obtained handle by calling <b>pfnReleaseSourceModeSet</b>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNSOURCEMODESET data types are defined in <i>D3dkmdt.h</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_createnewsourcemodeset.md">pfnCreateNewSourceModeSet</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md">pfnAcquireSourceModeSet</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPN_RELEASESOURCEMODESET callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>