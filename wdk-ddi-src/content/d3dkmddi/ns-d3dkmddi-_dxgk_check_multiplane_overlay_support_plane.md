---
UID : NS:d3dkmddi._DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
title : _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
author : windows-driver-content
description : Specifies the support attributes that the hardware provides for multiplane overlays.
old-location : display\dxgk_check_multiplane_overlay_support_plane.htm
old-project : display
ms.assetid : 28CC4BE1-D4C1-4D22-885B-D50BE5AD6EE6
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmddi.h
req.include-header : D3dkmddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
req.alt-loc : D3dkmddi.h
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
req.typenames : DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
---

# _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE structure
Specifies the support attributes that the hardware provides for multiplane overlays.

## Syntax
````
typedef struct _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE {
  HANDLE                             hAllocation;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID     VidPnSourceId;
  DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES PlaneAttributes;
} DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE;
````

## Members

        
            `hAllocation`

            [out] A handle to the allocation. The display miniport driver must set this member to a value that it can use to refer to its private tracking structure for the allocation.
        
            `PlaneAttributes`

            A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_attributes.md">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a> structure that specifies overlay plane attributes.
        
            `VidPnSourceId`

            [in] The zero-based video present network (VidPN) source identification number of the input for which the support levels are queried.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_attributes.md">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>