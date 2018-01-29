---
UID : NS:d3dkmddi._DXGKARG_RECOMMENDVIDPNTOPOLOGY
title : _DXGKARG_RECOMMENDVIDPNTOPOLOGY
author : windows-driver-content
description : The DXGKARG_RECOMMENDVIDPNTOPOLOGY structure contains arguments for the display miniport driver's DxgkDdiRecommendVidPnTopology function.
old-location : display\dxgkarg_recommendvidpntopology.htm
old-project : display
ms.assetid : 9a3efdc8-4534-4de6-89f8-42d94ba8b9a6
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : DmStructs_960673e2-caf0-4f46-9b8c-c1da025fb6bf.xml, d3dkmddi/DXGKARG_RECOMMENDVIDPNTOPOLOGY, DXGKARG_RECOMMENDVIDPNTOPOLOGY structure [Display Devices], _DXGKARG_RECOMMENDVIDPNTOPOLOGY, DXGKARG_RECOMMENDVIDPNTOPOLOGY, display.dxgkarg_recommendvidpntopology
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmddi.h
req.include-header : D3dkmddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGKARG_RECOMMENDVIDPNTOPOLOGY
---

# _DXGKARG_RECOMMENDVIDPNTOPOLOGY structure
The DXGKARG_RECOMMENDVIDPNTOPOLOGY structure contains arguments for the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendvidpntopology.md">DxgkDdiRecommendVidPnTopology</a> function.

## Syntax
````
typedef struct _DXGKARG_RECOMMENDVIDPNTOPOLOGY {
  D3DKMDT_HVIDPN                     hVidPn;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID     VidPnSourceId;
  DXGK_RECOMMENDVIDPNTOPOLOGY_REASON RequestReason;
  D3DKMDT_HVIDPNTOPOLOGY             hFallbackTopology;
} DXGKARG_RECOMMENDVIDPNTOPOLOGY;
````

## Members


`hFallbackTopology`

A handle to a VidPN topology object that represents the fallback VidPN topology that Windows will use if the miniport does not provide a topology recommendation.

`hVidPn`

A handle to a VidPN object. The <i>DxgkDdiRecommendVidPnTopology</i> function creates or augments the topology of this VidPN.

`RequestReason`

A value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_recommendvidpntopology_reason.md">DXGK_RECOMMENDVIDPNTOPOLOGY_REASON</a> enumeration that indicates the reason that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendvidpntopology.md">DxgkDdiRecommendVidPnTopology</a> function is being called.

`VidPnSourceId`

D3DDDI_ID_ALL or the identifier of a particular video present source on the display adapter. If this member is the identifier of a particular source, the <i>DxgkDdiRecommendVidPnTopology</i> function must augment the topology by adding at least one path that originates from that source. If this member is equal to D3DDDI_ID_ALL, <i>DxgkDdiRecommendVidPnTopology</i> must create the entire topology.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendvidpntopology.md">DxgkDdiRecommendVidPnTopology</a>

<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_recommendvidpntopology_reason.md">DXGK_RECOMMENDVIDPNTOPOLOGY_REASON</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_RECOMMENDVIDPNTOPOLOGY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>