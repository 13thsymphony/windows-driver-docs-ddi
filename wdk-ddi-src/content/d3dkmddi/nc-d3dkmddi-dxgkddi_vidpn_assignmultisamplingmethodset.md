---
UID: NC.d3dkmddi.DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET
title: DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET
author: windows-driver-content
description: The pfnAssignMultisamplingMethodSet function assigns a set of multisampling methods to a particular video present source in a specified VidPN.
old-location: display\dxgk_vidpn_interface_pfnassignmultisamplingmethodset.htm
old-project: display
ms.assetid: 607e3294-7399-446c-b07c-f0d5416b997e
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
req.alt-api: pfnAssignMultisamplingMethodSet
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

# DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET callback



## -description
The <b>pfnAssignMultisamplingMethodSet</b> function assigns a set of multisampling methods to a particular video present source in a specified VidPN.


## -prototype

````
DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET pfnAssignMultisamplingMethodSet;

NTSTATUS APIENTRY pfnAssignMultisamplingMethodSet(
  _In_       D3DKMDT_HVIDPN                 hVidPn,
  _In_ const D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId,
  _In_ const SIZE_T                         NumMethods,
  _In_ const D3DDDI_MULTISAMPLINGMETHOD     *pSupportedMethodSet
)
{ ... }
````


## -parameters

### -param hVidPn [in]

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>.

### -param VidPnSourceId [in]

[in] An integer that identifies one of the video present sources associated with the VidPN object.

### -param NumMethods [in]

[in] The number of elements in the <i>pSupportedMethodSet</i> array.

### -param pSupportedMethodSet [in]

[in] A pointer to an array of <a href="display.d3dddi_multisamplingmethod">D3DDDI_MULTISAMPLINGMETHOD</a> structures, each of which describes a multisampling method.

## -returns
The <b>pfnAssignMultisamplingMethodSet</b> function returns one of the following values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN</b></dt>
</dl>The handle supplied in <i>hVidPn</i> was invalid.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>The identifier supplied in <i>VidPnSourceId</i> was invalid.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>The function failed because it was unable to allocate enough memory.

 

This function might also return other error codes that are defined in Ntstatus.h.

## -remarks


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
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
