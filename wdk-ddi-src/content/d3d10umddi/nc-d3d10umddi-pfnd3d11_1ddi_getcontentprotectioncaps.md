---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS
title: PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS
author: windows-driver-content
description: Queries the available content protection for a specified encryption algorithm and video decoder profile.
old-location: display\getcontentprotectioncaps.htm
old-project: display
ms.assetid: 51024d63-f58c-45a7-bd6f-9f24a6805878
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS, d3d10umddi/pfnGetContentProtectionCaps, display.getcontentprotectioncaps, pfnGetContentProtectionCaps, pfnGetContentProtectionCaps callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	pfnGetContentProtectionCaps
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS callback function
Queries the available content protection for a specified encryption algorithm and video decoder profile.

## Syntax

```
PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS Pfnd3d111DdiGetcontentprotectioncaps;

HRESULT Pfnd3d111DdiGetcontentprotectioncaps(
  D3D10DDI_HDEVICE hDevice,
  CONST GUID *pCryptoType,
  CONST GUID *pDecodeProfile,
  D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS *pCaps
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*pCryptoType`

A pointer to a GUID that specifies the type of encryption algorithm to query.

`*pDecodeProfile`

A pointer to a GUID that specifies the decoder profile to query.

`*pCaps`

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps.md">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a> structure that contains the protection capabilities for the specified encryption algorithm and decoder profile.


## Return Value

<b>GetContentProtectionCaps</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The content protection capabilities were queried successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DERR_INVALID_CRYPTO</b></dt>
</dl>
</td>
<td width="60%">
The encryption algorithm specified by the <i>pCryptoType</i> parameter is not supported.

</td>
</tr>
</table>

## Remarks

The <i>pCryptoType</i> parameter can contain one of the following values:

<ul>
<li>
<b>D3DCRYPTOTYPE_AES128_CTR</b> if the driver is configured to use the 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher.


</li>
<li>
<b>D3DCRYPTOTYPE_PROPRIETARY</b> if the driver is configured to use a proprietary encryption algorithm.


</li>
<li>
<b>NULL_GUID</b> if the driver is not configured to use any encryption algorithm.

</li>
</ul>
<div class="alert"><b>Note</b>  The Microsoft Direct3D runtime verifies that the  <i>pDecodeProfile</i> and <i>pCryptoType</i> parameter data is valid before it calls the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle.md">GetContentProtectionCaps</a> function.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps.md">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a>