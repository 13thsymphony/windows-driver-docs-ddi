---
UID: NC:d3dkmddi.DXGKDDI_RECOMMENDVIDPNTOPOLOGY
title: DXGKDDI_RECOMMENDVIDPNTOPOLOGY function
author: windows-driver-content
description: The DxgkDdiRecommendVidPnTopology function creates the topology of a specified VidPN or augments the topology with a new path to video present targets.
old-location: display\dxgkddirecommendvidpntopology.htm
old-project: display
ms.assetid: a7c31d2c-3893-4d25-837d-d4650aeb1cd1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_RECOMMENDVIDPNTOPOLOGY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiRecommendVidPnTopology
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

# DXGKDDI_RECOMMENDVIDPNTOPOLOGY function



## -description
The <i>DxgkDdiRecommendVidPnTopology</i> function creates the topology of a specified VidPN or augments the topology with a new path to video present targets.



## -syntax

````
DXGKDDI_RECOMMENDVIDPNTOPOLOGY DxgkDdiRecommendVidPnTopology;

NTSTATUS APIENTRY DxgkDdiRecommendVidPnTopology(
  _In_ const HANDLE                               hAdapter,
  _In_ const DXGKARG_RECOMMENDVIDPNTOPOLOGY CONST *pRecommendVidPnTopologyArg
)
{ ... }
````


## -parameters

### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pRecommendVidPnTopologyArg [in]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_recommendvidpntopology.md">DXGKARG_RECOMMENDVIDPNTOPOLOGY</a> structure that contains function arguments.


## -returns
<i>DxgkDdiRecommendVidPnTopology </i>returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function successfully created or augmented the topology.
<dl>
<dt><b>STATUS_GRAPHICS_NO_RECOMMENDED_VIDPN_TOPOLOGY</b></dt>
</dl>The function has no recommendation for the augmentation of the specified VidPN topology. 
<dl>
<dt><b>STATUS_GRAPHICS_CANCEL_VIDPN_TOPOLOGY_AUGMENTATION</b></dt>
</dl>The function recommends to cancel the augmentation of the specified VidPN's topology on the specified source. This return code is allowed only in the case of VidPN topology augmentation. 
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>The function failed because it was unable to allocate enough memory.

 

The miniport driver should pass through any error code that it gets from the operating system for which it does not have a fallback code path.


## -remarks
<i>DxgkDdiRecommendVidPnTopology</i>
     should be made pageable.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570560">VidPn Topology Interface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_RECOMMENDVIDPNTOPOLOGY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

