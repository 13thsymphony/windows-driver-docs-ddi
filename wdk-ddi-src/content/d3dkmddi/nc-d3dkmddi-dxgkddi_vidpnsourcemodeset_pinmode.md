---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_PINMODE
title: DXGKDDI_VIDPNSOURCEMODESET_PINMODE
author: windows-driver-content
description: The pfnPinMode function pins a specified mode in a VidPN source mode set.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnpinmode.htm
old-project: display
ms.assetid: 14bbdc35-e633-49a5-bdf0-6b60d330ca8e
ms.author: windowsdriverdev
ms.date: 12/29/2017
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
req.alt-api: pfnPinMode
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
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNSOURCEMODESET_PINMODE callback



## -description
The <b>pfnPinMode</b> function pins a specified mode in a VidPN source mode set.



## -prototype

````
DXGKDDI_VIDPNSOURCEMODESET_PINMODE pfnPinMode;

NTSTATUS APIENTRY pfnPinMode(
  _In_       D3DKMDT_HVIDPNSOURCEMODESET          hVidPnSourceModeSet,
  _In_ const D3DKMDT_VIDEO_PRESENT_SOURCE_MODE_ID VidPnSourceModeId
)
{ ... }
````


## -parameters

### -param hVidPnSourceModeSet [in]

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md">pfnAcquireSourceModeSet</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


### -param VidPnSourceModeId [in]

[in] An integer that identifies the mode to be pinned.


## -returns
The <b>pfnPinMode</b> function returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded. 
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET</b></dt>
</dl>The handle supplied in <i>hVidPnSourceModeSet</i> was invalid.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE_MODE</b></dt>
</dl>The mode identified by <i>VidPnSourceModeId</i> does not belong to the source mode set represented by <i>hVidPnSourceModeSet</i>.

 


## -remarks
VidPN source mode identifiers are assigned by the operating system. The <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a> function generates a mode identifier, assigns the identifier to the <b>Id</b> member of a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a> structure, and returns the structure to the display miniport driver.

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
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirepinnedmodeinfo.md">pfnAcquirePinnedModeInfo</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNSOURCEMODESET_PINMODE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

