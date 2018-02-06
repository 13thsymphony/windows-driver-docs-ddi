---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO
title: DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO
author: windows-driver-content
description: The pfnReleaseModeInfo function releases a D3DKMDT_VIDPN_TARGET_MODE structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_vidpntargetmodeset_interface_pfnreleasemodeinfo.htm
old-project: display
ms.assetid: 0b1d0331-f0fa-40fc-a1d6-15fe3568f3cc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_vidpntargetmodeset_interface_pfnreleasemodeinfo, pfnReleaseModeInfo callback function [Display Devices], pfnReleaseModeInfo, DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO, DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO, d3dkmddi/pfnReleaseModeInfo, VidPnFunctions_faa4fee3-0bf7-43af-a000-e5b7e891c9e9.xml
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
-	pfnReleaseModeInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO callback function
The <b>pfnReleaseModeInfo</b> function releases a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md">D3DKMDT_VIDPN_TARGET_MODE</a> structure that the VidPN manager previously provided to the display miniport driver.

## Syntax

```
DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO DxgkddiVidpntargetmodesetReleasemodeinfo;

NTSTATUS DxgkddiVidpntargetmodesetReleasemodeinfo(
  IN_CONST_D3DKMDT_HVIDPNTARGETMODESET hVidPnTargetModeSet,
  IN_CONST_PD3DKMDT_VIDPN_TARGET_MODE_CONST pVidPnTargetModeInfo
)
{...}
```

## Parameters

`hVidPnTargetModeSet`

[in] A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset.md">pfnAcquireTargetModeSet</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.

`pVidPnTargetModeInfo`

[in] A pointer to the D3DKMDT_VIDPN_TARGET_MODE structure that is to be released.


## Return Value

The <b>pfnReleaseModeInfo</b> function returns one of the following values:
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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTargetModeSet</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET_MODE</b></dt>
</dl>
</td>
<td width="60%">
The pointer supplied in <i>pVidPnTargetModeInfo</i> was invalid.

</td>
</tr>
</table>

## Remarks

When you have finished using a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md">D3DKMDT_VIDPN_TARGET_MODE</a> structure that you obtained by calling any of the following functions, you must release the structure by calling <b>pfnReleaseModeInfo</b>.
<ul>
<li>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a>


</li>
<li>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirenextmodeinfo.md">pfnAcquireNextModeInfo</a>


</li>
<li>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirepinnedmodeinfo.md">pfnAcquirePinnedModeInfo</a>


</li>
</ul>If you obtain a D3DKMDT_VIDPN_TARGET_MODE structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a> and then pass that structure to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_addmode.md">pfnAddMode</a>, you do not need to release the structure.

If you obtain a handle by calling <b>pfnCreateNewModeInfo</b> and then you decide not to add the new mode to a target mode set, you must release the newly created structure by calling <b>pfnReleaseModeInfo</b>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirenextmodeinfo.md">pfnAcquireNextModeInfo</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirepinnedmodeinfo.md">pfnAcquirePinnedModeInfo</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md">D3DKMDT_VIDPN_TARGET_MODE</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>