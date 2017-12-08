---
UID: NC.d3dkmddi.DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET
title: DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET
author: windows-driver-content
description: The pfnGetMonitorFrequencyRangeSet function returns a handle to the monitor frequency range set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_pfngetmonitorfrequencyrangeset.htm
old-project: display
ms.assetid: 78b80dbb-af1e-457c-854f-ff0404ab9808
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
req.alt-api: pfnGetMonitorFrequencyRangeSet
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

# DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET callback



## -description
The <b>pfnGetMonitorFrequencyRangeSet</b> function returns a handle to the monitor frequency range set object that is associated with a specified monitor.


## -prototype

````
DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET pfnGetMonitorFrequencyRangeSet;

NTSTATUS APIENTRY pfnGetMonitorFrequencyRangeSet(
  _In_  const D3DKMDT_ADAPTER                         hAdapter,
  _In_  const D3DDDI_VIDEO_PRESENT_TARGET_ID          VideoPresentTargetId,
  _Out_       PD3DKMDT_HMONITORFREQUENCYRANGESET      *phMonitorFrequencyRangeSet,
  _Out_ const DXGK_MONITORFREQUENCYRANGESET_INTERFACE **ppMonitorFrequencyRangeSetInterface
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a> function.

### -param VideoPresentTargetId [in]

[in] An integer that identifies one of the video present targets on the display adapter. The returned monitor frequency range set object describes the frequency ranges available on the monitor that is connected to this video present target.

### -param phMonitorFrequencyRangeSet [out]

[out] A pointer to a variable that receives a handle to the monitor frequency range set object.

### -param ppMonitorFrequencyRangeSetInterface [out]

[out] A pointer to a variable that receives a pointer to a <a href="display.dxgk_monitorfrequencyrangeset_interface">DXGK_MONITORFREQUENCYRANGESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the monitor frequency range set object.

## -returns
The <b>pfnGetMonitorFrequencyRangeSet</b> function returns one of the following values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was supplied.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER</b></dt>
</dl>The handle supplied in <i>hAdapter</i> was invalid.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET</b></dt>
</dl>The identifier supplied in <i>VideoPresentTargetId</i> was invalid.
<dl>
<dt><b>STATUS_GRAPHICS_MONITOR_NOT_CONNECTED</b></dt>
</dl>There is no monitor connected to the video present target identified by <i>VideoPresentTargetId</i>.

 

This function might also return other error codes that are defined in <i>Ntstatus.h</i>.

## -remarks
VidPN target identifiers are assigned by the display miniport driver. The <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a><i></i><u>function</u>, implemented by the display miniport driver, returns an array of <a href="display.dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

You do not need to release the handle returned in <i>phMonitorFrequencyRangeSet</i>.

This function is also available in the <a href="display.dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7.

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
<a href="display.dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
