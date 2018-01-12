---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_GETTOPOLOGY
title: DXGKDDI_VIDPN_GETTOPOLOGY
author: windows-driver-content
description: The pfnGetTopology function returns a handle to the VidPN topology object contained by a specified VidPN object.
old-location: display\dxgk_vidpn_interface_pfngettopology.htm
old-project: display
ms.assetid: 2bc43cd0-97a2-4120-8e6f-425664d3d28c
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
req.alt-api: pfnGetTopology
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

# DXGKDDI_VIDPN_GETTOPOLOGY callback



## -description
The <b>pfnGetTopology</b> function returns a handle to the VidPN topology object contained by a specified VidPN object.



## -prototype

````
DXGKDDI_VIDPN_GETTOPOLOGY pfnGetTopology;

NTSTATUS APIENTRY pfnGetTopology(
  _In_  const D3DKMDT_HVIDPN               hVidPn,
  _Out_       D3DKMDT_HVIDPNTOPOLOGY       *phVidPnTopology,
  _Out_ const DXGK_VIDPNTOPOLOGY_INTERFACE **ppVidPnTopologyInterface
)
{ ... }
````


## -parameters

### -param hVidPn [in]

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a>, or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a>.


### -param phVidPnTopology [out]

[out] A pointer to a variable that receives a handle to the VidPN topology object.


### -param ppVidPnTopologyInterface [out]

[out] A pointer to a variable that receives a pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpntopology_interface.md">DXGK_VIDPNTOPOLOGY_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the VidPN topology object.


## -returns
The <b>pfnGetTopology</b> function returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN</b></dt>
</dl>The handle supplied in <i>hVidPn</i> was invalid.

 


## -remarks
The display miniport driver does not need to release the handle that it receives in <i>phVidPnTopology</i>.

The lifetime of the DXGK_VIDPNTOPOLOGY_INTERFACE structure returned in <i>ppVidPnTopologyInterface</i> is owned by the operating system. Using this ownership scheme, the operating system can migrate to newer implementations at run time without breaking clients of the interface. 


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570560">VidPN Topology Interface</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpntopology_interface.md">DXGK_VIDPNTOPOLOGY_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPN_GETTOPOLOGY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

