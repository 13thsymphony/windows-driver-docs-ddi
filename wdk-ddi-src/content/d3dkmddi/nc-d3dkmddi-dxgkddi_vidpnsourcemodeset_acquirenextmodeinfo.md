---
UID: NC.d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO
title: DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO
author: windows-driver-content
description: The pfnAcquireNextModeInfo function returns a descriptor of the next mode in a specified VidPN source mode set, given the current mode.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnacquirenextmodeinfo.htm
old-project: display
ms.assetid: d9cb1ff1-c428-46e5-884a-5fc39e16300e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
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
req.alt-api: pfnAcquireNextModeInfo
req.alt-loc: d3dkmddi.h
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
---

# DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO callback



## -description
The <b>pfnAcquireNextModeInfo</b> function returns a descriptor of the next mode in a specified VidPN source mode set, given the current mode.


## -prototype

````
DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO pfnAcquireNextModeInfo;

NTSTATUS APIENTRY pfnAcquireNextModeInfo(
  _In_  const D3DKMDT_HVIDPNSOURCEMODESET     hVidPnSourceModeSet,
  _In_  const D3DKMDT_VIDPN_SOURCE_MODE CONST *pVidPnSourceModeInfo,
  _Out_ const D3DKMDT_VIDPN_SOURCE_MODE       **ppNextVidPnSourceModeInfo
)
{ ... }
````


## -parameters

### -param hVidPnSourceModeSet [in]

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md">pfnAcquireSourceModeSet</a> function of the <a href="display.dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param pVidPnSourceModeInfo [in]

[in] A pointer to a <a href="display.d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure that describes the current mode. The display miniport driver previously obtained this pointer by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a> or <b>pfnAcquireNextModeInfo</b>.

### -param ppNextVidPnSourceModeInfo [out]

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_SOURCE_MODE structure that describes the next mode.

## -returns
The <b>pfnAcquireNextModeInfo</b> function returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET</b></dt>
</dl>The handle supplied in <i>hVidPnSourceModeSet</i> was invalid.

 

## -remarks
When you have finished using the <a href="display.d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure, you must release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo.md">pfnReleaseModeInfo</a>.

You can enumerate all the modes that belong to a VidPN source mode set object by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a> and then making a sequence of calls to <b>pfnAcquireNextModeInfo</b>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo.md">pfnReleaseModeInfo</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a>
</dt>
<dt>
<a href="display.d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
