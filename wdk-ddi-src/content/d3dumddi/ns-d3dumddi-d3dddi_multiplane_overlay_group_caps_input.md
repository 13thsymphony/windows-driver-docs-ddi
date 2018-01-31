---
UID : NS:d3dumddi.D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT
title : D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT
author : windows-driver-content
description : Specifies info on a multiplane overlay capability group.
old-location : display\d3dddi_multiplane_overlay_group_caps_input.htm
old-project : display
ms.assetid : 0AF66863-A1C0-4BCF-A677-BAF7F2961390
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dumddi/PD3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT, D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT, display.d3dddi_multiplane_overlay_group_caps_input, D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT structure [Display Devices], PD3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT structure pointer [Display Devices], PD3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dumddi.h
req.include-header : TBD
req.target-type : Windows
req.target-min-winverclnt : 
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT
---

# D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT structure
Specifies info on a multiplane overlay capability group.

## Syntax
````
typedef struct D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  UINT                           GroupIndex;
} D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT, *PD3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT;
````

## Members


`GroupIndex`

[in] The index of the overlay capability group for which capabilities are queried. This value is always between zero and (<a href="..\d3dumddi\ns-d3dumddi-d3dddi_multiplane_overlay_caps.md">D3DDDI_MULTIPLANE_OVERLAY_CAPS</a>.<b>NumCapabilityGroups</b> – 1).

`VidPnSourceId`

[in] The zero-based video present network (VidPN) source identification number of the input for which the capabilities are queried.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include TBD) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-d3dddi_multiplane_overlay_caps.md">D3DDDI_MULTIPLANE_OVERLAY_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_MULTIPLANE_OVERLAY_GROUP_CAPS_INPUT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>