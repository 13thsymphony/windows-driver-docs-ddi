---
UID: NS.D3DKMDDI._DXGKARG_QUERYVIDPNHWCAPABILITY
title: _DXGKARG_QUERYVIDPNHWCAPABILITY
author: windows-driver-content
description: The DXGKARG_QUERYVIDPNHWCAPABILITY structure is used by the display miniport driver to describe the hardware capabilities of a functional VidPN in response to a call to the DxgkDdiQueryVidPnHWCapability function.
old-location: display\dxgkarg_queryvidpnhwcapability.htm
old-project: display
ms.assetid: b5f8073c-9989-4413-842d-e3e295cc3470
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGKARG_QUERYVIDPNHWCAPABILITY, DXGKARG_QUERYVIDPNHWCAPABILITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_QUERYVIDPNHWCAPABILITY;typedef __inout DXGKARG_QUERYVIDPNHWCAPABILITY* INOUT_PDXGKARG_QUERYVIDPNHWCAPABILITY
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

# _DXGKARG_QUERYVIDPNHWCAPABILITY structure



## -description
The DXGKARG_QUERYVIDPNHWCAPABILITY structure is used by the display miniport driver to describe the hardware capabilities of a functional VidPN in response to a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryvidpnhwcapability.md">DxgkDdiQueryVidPnHWCapability</a> function.



## -syntax

````
typedef struct _DXGKARG_QUERYVIDPNHWCAPABILITY {
  D3DKMDT_HVIDPN                 hFunctionalVidPn;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID SourceId;
  D3DDDI_VIDEO_PRESENT_TARGET_ID TargetId;
  D3DKMDT_VIDPN_HW_CAPABILITY    VidPnHWCaps;
} DXGKARG_QUERYVIDPNHWCAPABILITY; typedef __inout DXGKARG_QUERYVIDPNHWCAPABILITY*  INOUT_PDXGKARG_QUERYVIDPNHWCAPABILITY;
````


## -struct-fields

### -field hFunctionalVidPn

[in] A handle to a functional VidPN object for which the hardware capabilities are being queried.


### -field SourceId

[in] An integer that identifies a video present source on the display adapter.


### -field TargetId

[in] An integer that identifies a video present target on the display adapter.


### -field VidPnHWCaps

[out] A <a href="display.d3dkmdt_vidpn_hw_capability">D3DKMDT_VIDPN_HW_CAPABILITY</a> structure that describes the capabilities of the display miniport driver to perform display operations without dedicated GPU hardware support.


## -remarks
The D3DDDI_VIDEO_PRESENT_SOURCE_ID and D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in <i>D3dukmdt.h</i>.

Video present source identifiers are assigned by the operating system. <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

Video present target identifiers are assigned by the display miniport driver. <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="display.dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

For more information about video present sources and targets, see <a href="https://msdn.microsoft.com/62a92f00-b1da-41c2-99af-eef8140b064e">Introduction to Video Present Networks</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of the Windows operating systems.

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
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmdt_video_present_source">D3DKMDT_VIDEO_PRESENT_SOURCE</a>
</dt>
<dt>
<a href="display.d3dkmdt_video_present_target">D3DKMDT_VIDEO_PRESENT_TARGET</a>
</dt>
<dt>
<a href="display.d3dkmdt_vidpn_hw_capability">D3DKMDT_VIDPN_HW_CAPABILITY</a>
</dt>
<dt>
<a href="display.d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryvidpnhwcapability.md">DxgkDdiQueryVidPnHWCapability</a>
</dt>
<dt>
<a href="display.dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_QUERYVIDPNHWCAPABILITY structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

