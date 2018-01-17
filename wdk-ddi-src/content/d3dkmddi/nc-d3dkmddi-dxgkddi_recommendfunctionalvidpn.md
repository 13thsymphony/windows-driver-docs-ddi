---
UID: NC:d3dkmddi.DXGKDDI_RECOMMENDFUNCTIONALVIDPN
title: DXGKDDI_RECOMMENDFUNCTIONALVIDPN function
author: windows-driver-content
description: The DxgkDdiRecommendFunctionalVidPn function creates a functional VidPN that can be implemented on a specified display adapter.
old-location: display\dxgkddirecommendfunctionalvidpn.htm
old-project: display
ms.assetid: 320a77a7-d7d4-47b9-8a40-2b6e12819e4b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_RECOMMENDFUNCTIONALVIDPN
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
req.alt-api: DxgkDdiRecommendFunctionalVidPn
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

# DXGKDDI_RECOMMENDFUNCTIONALVIDPN function



## -description
The <i>DxgkDdiRecommendFunctionalVidPn</i> function creates a functional VidPN that can be implemented on a specified display adapter.



## -syntax

````
DXGKDDI_RECOMMENDFUNCTIONALVIDPN DxgkDdiRecommendFunctionalVidPn;

NTSTATUS APIENTRY DxgkDdiRecommendFunctionalVidPn(
  _In_ const HANDLE                                 hAdapter,
  _In_ const DXGKARG_RECOMMENDFUNCTIONALVIDPN CONST *pRecommendFunctionalVidPnArg
)
{ ... }
````


## -parameters

### -param hAdapter [in]

A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pRecommendFunctionalVidPnArg [in]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_recommendfunctionalvidpn.md">DXGKARG_RECOMMENDFUNCTIONALVIDPN</a> structure that contains function arguments. The caller supplies the <b>hRecommendedFunctionalVidPn</b> member, which is a handle to an empty VidPN object. <i>DxgkDdiRecommendFunctionalVidPn</i> populates the VidPN object with the elements of a functional VidPN: topology, mode sets, pinned modes.


## -returns
<i>DxgkDdiRecommendFunctionalVidPn </i>returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded in creating a functional VidPN.
<dl>
<dt><b>STATUS_GRAPHICS_NO_RECOMMENDED_FUNCTIONAL_VIDPN</b></dt>
</dl>The function was not able to create a functional VidPN.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>The function failed because it was unable to allocate memory.

 


## -remarks
A VidPN is functional if it satisfies the following conditions:

It has a topology that has at least one path. (A path is an association between a source and a target.)

Every source and target in the topology has a pinned mode.

The job of <i>DxgkDdiRecommendFunctionalVidPn</i> is to create a functional VidPN that can be implemented on the display adapter. The following list gives the steps used to create a functional VidPN.

Start with a handle to an empty VidPN object. This handle was supplied in the <b>hDesiredVidPn</b> member of <i>pRecommendFunctionalVidPnArg.</i>

Add a path (source-target pair) to the topology of the VidPN.

Create a new source mode set and add one source mode to the set. Assign the source mode set to the source in your path. Pin the source mode. 

Create a new target mode set and add one target mode to the set. Assign the target mode set to the target in your path. Pin the target mode.

For information about how to add paths, add mode sets, assign modes, and pin modes, see <a href="https://msdn.microsoft.com/5dedac8c-9a99-4b3a-81be-39819135cd97">VidPN Objects and Interfaces</a>.

<i>DxgkDdiRecommendFunctionalVidPn</i> should be made pageable.</p>