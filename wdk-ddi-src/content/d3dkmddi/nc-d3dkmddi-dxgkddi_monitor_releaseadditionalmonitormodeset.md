---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET
title: DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET
author: windows-driver-content
description: The pfnReleaseAdditionalMonitorModeSet function, available in the DXGK_MONITOR_INTERFACE_V2 interface beginning with Windows 7, releases a handle to an additional monitor source mode set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_v2_pfnreleaseadditionalmonitormodeset.htm
old-project: display
ms.assetid: b9f6cb52-8870-4319-a1ff-d3dbbeef8cb6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_MAPCPUHOSTAPERTURE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnReleaseAdditionalMonitorModeSet
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
req.typenames: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
---

# DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET callback



## -description
The <b>pfnReleaseAdditionalMonitorModeSet</b> function, available in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface_v2.md">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7, releases a handle to an additional monitor source mode set object that is associated with a specified monitor.



## -prototype

````
DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET pfnReleaseAdditionalMonitorModeSet;

NTSTATUS APIENTRY pfnReleaseAdditionalMonitorModeSet(
  _In_ const D3DKMDT_ADAPTER                hAdapter,
  _In_ const D3DDDI_VIDEO_PRESENT_TARGET_ID VideoPresentTargetId,
  _In_ const DXGK_TARGETMODE_DETAIL_TIMING  *pAdditionalModesSet
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


### -param VideoPresentTargetId [in]

[in] An integer that identifies one of the video present targets on the display adapter. The additional modes set object <i>ppAdditionalModesSet</i> returned in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md">pfnGetAdditionalMonitorModeSet</a> function describes the additional monitor source mode sets that are available on the monitor that is connected to this video present target.


### -param pAdditionalModesSet [in]

[in] A pointer to a variable that receives a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_targetmode_detail_timing.md">DXGK_TARGETMODE_DETAIL_TIMING</a> structure that describes a video present target's additional timing modes that are compatible with the display device. This structure was initially obtained in a call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md">pfnGetAdditionalMonitorModeSet</a>.


## -returns
The <b>pfnReleaseAdditionalMonitorModeSet</b> function returns one of the following values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER</b></dt>
</dl>The handle supplied in <i>hAdapter</i> was invalid.
<dl>
<dt><b>STATUS_INVALID_MONITOR_SOURCEMODESET</b></dt>
</dl>The handle supplied in <i>ppAdditionalModesSet</i> was invalid.

 


## -remarks
This function is available beginning with Windows 7.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface_v2.md">DXGK_MONITOR_INTERFACE_V2</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md">DXGK_MONITOR_INTERFACE_V2::pfnGetAdditionalMonitorModeSet</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

