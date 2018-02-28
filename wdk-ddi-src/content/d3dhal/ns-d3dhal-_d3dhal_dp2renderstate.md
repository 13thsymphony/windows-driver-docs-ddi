---
UID: NS:d3dhal._D3DHAL_DP2RENDERSTATE
title: "_D3DHAL_DP2RENDERSTATE"
author: windows-driver-content
description: One or more D3DHAL_DP2RENDERSTATE structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_RENDERSTATE, and are used to set the appropriate render state.
old-location: display\d3dhal_dp2renderstate.htm
old-project: display
ms.assetid: 9d30ed5d-0621-4a90-941c-c5b0564df13f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*LPD3DHAL_DP2RENDERSTATE, D3DHAL_DP2RENDERSTATE, D3DHAL_DP2RENDERSTATE structure [Display Devices], LPD3DHAL_DP2RENDERSTATE, LPD3DHAL_DP2RENDERSTATE structure pointer [Display Devices], _D3DHAL_DP2RENDERSTATE, d3dhal/D3DHAL_DP2RENDERSTATE, d3dhal/LPD3DHAL_DP2RENDERSTATE, d3dstrct_4cfe9ea2-c3cc-432d-bd11-85d51ba121b5.xml, display.d3dhal_dp2renderstate"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2RENDERSTATE
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2RENDERSTATE
---

# _D3DHAL_DP2RENDERSTATE structure
One or more D3DHAL_DP2RENDERSTATE structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_RENDERSTATE, and are used to set the appropriate render state.

## Syntax
````
typedef struct _D3DHAL_DP2RENDERSTATE {
  D3DRENDERSTATETYPE RenderState;
  union {
    D3DVALUE dvState;
    DWORD    dwState;
  };
} D3DHAL_DP2RENDERSTATE, *LPD3DHAL_DP2RENDERSTATE;
````

## Members


`RenderState`

Specifies a D3DRENDERSTATETYPE enumerated type that indicates the render state to be updated. Render states that are requested at the application level are described in the DirectX SDK documentation. Render states that are exclusively used by drivers are described in <a href="..\d3d9types\ne-d3d9types-_d3drenderstatetype.md">D3DRENDERSTATETYPE</a>.

## Remarks
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should process <b>wStateCount</b> D3DHAL_DP2RENDERSTATE structures from the command buffer. The value of <b>wStateCount</b> is specified in the D3DHAL_DP2COMMAND structure.

For each D3DHAL_DP2RENDERSTATE structure, <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should update the driver's private render state and the render state array that the <b>lpdwRStates</b> member of <a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a> points to. The element to be updated in the public render state array is <b>lpdwRStates[RenderState]</b>.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_RENDERSTATE command and two D3DHAL_DP2RENDERSTATE structures. The driver should update <b>lpdwRStates</b>[D3DRENDERSTATE_FILLMODE] to be D3DFILL_SOLID and <b>lpdwRStates</b>[D3DRENDERSTATE_SHADEMODE] to be D3DSHADE_GOURAUD. The driver should also update its private state accordingly.

<img alt="Figure showing a command buffer with a D3DDP2OP_RENDERSTATE command and two D3DHAL_DP2RENDERSTATE structures" src="images/dp2rs.png"/>
Although render states whose values are Boolean in type are documented as only accepting <b>TRUE</b>(1) and <b>FALSE</b>(0) the runtime does not validate this and accepts any subzero value as true. The sample driver interprets this strictly and does interpret values other than 1 as being <b>TRUE</b>. However, because the runtime does not offer validation, your driver should interpret 0 as <b>FALSE</b> and any other subzero value as <b>TRUE</b>. In this respect your driver should not mimic the behavior of the supplied sample driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



<a href="..\d3d9types\ne-d3d9types-_d3drenderstatetype.md">D3DRENDERSTATETYPE</a>



D3DDP2OP_RENDERSTATE



<a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2RENDERSTATE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>