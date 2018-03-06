---
UID: NC:d3dkmddi.DXGKDDI_RECOMMENDVIDPNTOPOLOGY
title: DXGKDDI_RECOMMENDVIDPNTOPOLOGY
author: windows-driver-content
description: The DxgkDdiRecommendVidPnTopology function creates the topology of a specified VidPN or augments the topology with a new path to video present targets.
old-location: display\dxgkddirecommendvidpntopology.htm
old-project: display
ms.assetid: a7c31d2c-3893-4d25-837d-d4650aeb1cd1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_RECOMMENDVIDPNTOPOLOGY, DmFunctions_8036db05-72c0-4b67-9151-a33da1df4fb8.xml, DxgkDdiRecommendVidPnTopology, DxgkDdiRecommendVidPnTopology callback function [Display Devices], d3dkmddi/DxgkDdiRecommendVidPnTopology, display.dxgkddirecommendvidpntopology
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiRecommendVidPnTopology
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_RECOMMENDVIDPNTOPOLOGY callback function
The <i>DxgkDdiRecommendVidPnTopology</i> function creates the topology of a specified VidPN or augments the topology with a new path to video present targets.

## Syntax

```
DXGKDDI_RECOMMENDVIDPNTOPOLOGY DxgkddiRecommendvidpntopology;

NTSTATUS DxgkddiRecommendvidpntopology(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARG_RECOMMENDVIDPNTOPOLOGY_CONST pRecommendVidPnTopology
)
{...}
```

## Parameters

`hAdapter`

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

`pRecommendVidPnTopology`




## Return Value

<i>DxgkDdiRecommendVidPnTopology </i>returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function successfully created or augmented the topology.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_NO_RECOMMENDED_VIDPN_TOPOLOGY</b></dt>
</dl>
</td>
<td width="60%">
The function has no recommendation for the augmentation of the specified VidPN topology. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_CANCEL_VIDPN_TOPOLOGY_AUGMENTATION</b></dt>
</dl>
</td>
<td width="60%">
The function recommends to cancel the augmentation of the specified VidPN's topology on the specified source. This return code is allowed only in the case of VidPN topology augmentation. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The function failed because it was unable to allocate enough memory.

</td>
</tr>
</table>
 

The miniport driver should pass through any error code that it gets from the operating system for which it does not have a fallback code path.

## Remarks

<i>DxgkDdiRecommendVidPnTopology</i>
     should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570560">VidPn Topology Interface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_RECOMMENDVIDPNTOPOLOGY callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>