---
UID : NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_CREATENEWMODEINFO
title : DXGKDDI_VIDPNSOURCEMODESET_CREATENEWMODEINFO
author : windows-driver-content
description : The pfnCreateNewModeInfo function returns a pointer to a D3DKMDT_VIDPN_SOURCE_MODE structure that the display miniport driver populates before calling pfnAddMode.
old-location : display\dxgk_vidpnsourcemodeset_interface_pfncreatenewmodeinfo.htm
old-project : display
ms.assetid : b18aab68-7457-45eb-8641-0b6180cfa70e
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
req.alt-api : pfnCreateNewModeInfo
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


# DXGKDDI_VIDPNSOURCEMODESET_CREATENEWMODEINFO callback function
The <b>pfnCreateNewModeInfo</b> function returns a pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a> structure that the display miniport driver populates before calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_addmode.md">pfnAddMode</a>.

## Syntax

```
DXGKDDI_VIDPNSOURCEMODESET_CREATENEWMODEINFO DxgkddiVidpnsourcemodesetCreatenewmodeinfo;

NTSTATUS DxgkddiVidpnsourcemodesetCreatenewmodeinfo(
  IN_CONST_D3DKMDT_HVIDPNSOURCEMODESET hVidPnSourceModeSet,
  DEREF_OUT_PPD3DKMDT_VIDPN_SOURCE_MODE ppNewVidPnSourceModeInfo
)
{...}
```

## Parameters

`hVidPnSourceModeSet`

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md">pfnAcquireSourceModeSet</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.

`ppNewVidPnSourceModeInfo`

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_SOURCE_MODE structure allocated by the VidPN manager.


## Return Value

The <b>pfnCreateNewModeInfo</b> function returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded. 
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET</b></dt>
</dl>The handle supplied in <i>hVidPnSourceModeSet</i> was invalid.

## Remarks

The <b>pfnCreateNewModeInfo</b> function allocates a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a> structure, sets its <b>Id</b> member to a newly generated identifier, and sets its <b>Type</b> member to <b>D3DKMDT_RMT_UNINITIALIZED</b>.

After you call <b>pfnCreateNewModeInfo</b> to obtain a D3DKMDT_VIDPN_SOURCE_MODE structure, you must do one, but not both, of the following:

Populate the structure and pass it to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_addmode.md">pfnAddMode</a>.

Release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo.md">pfnReleaseModeInfo</a>.

When you populate a D3DKMDT_VIDPN_SOURCE_MODE structure, you have the option of overwriting the <b>Id</b> member that was generated and set by <b>pfnCreateNewModeInfo</b>. However, if you overwrite the <b>Id</b> member of any D3DKMDT_VIDPN_SOURCE_MODE structure, you must overwrite the <b>Id</b> members of all the D3DKMDT_VIDPN_SOURCE_MODE structures you obtain from <b>pfnCreateNewModeInfo</b>. Unless you have a specific reason for overwriting the <b>Id</b> members (for example, tracking source modes with your own numbering scheme), you should leave them as set by <b>pfnCreateNewModeInfo</b>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>.

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
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_addmode.md">pfnAddMode</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo.md">pfnReleaseModeInfo</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNSOURCEMODESET_CREATENEWMODEINFO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>