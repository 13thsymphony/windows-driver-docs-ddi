---
UID: NS.D3DKMDDI._DXGK_PLANE_SPECIFIC_INPUT_FLAGS
title: _DXGK_PLANE_SPECIFIC_INPUT_FLAGS
author: windows-driver-content
description: A structure containing the input flags to be used for the driver that apply to a plane.
old-location: display\dxgk_plane_specific_input_flags.htm
old-project: display
ms.assetid: 39BE1343-D965-4750-9B94-B54127D873A5
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_PLANE_SPECIFIC_INPUT_FLAGS, DXGK_PLANE_SPECIFIC_INPUT_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_PLANE_SPECIFIC_INPUT_FLAGS
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

# _DXGK_PLANE_SPECIFIC_INPUT_FLAGS structure



## -description
A structure containing the input flags to be used for the driver that apply to a plane.



## -syntax

````
typedef struct _DXGK_PLANE_SPECIFIC_INPUT_FLAGS {
  union {
    struct {
      UINT Enabled  :1;
      UINT FlipImmediate  :1;
      UINT FlipOnNextVSync  :1;
      UINT SharedPrimaryTransition  :1;
      UINT IndependentFlipExclusive  :1;
      UINT Reserved  :27;
    };
    UINT Value;
  };
} DXGK_PLANE_SPECIFIC_INPUT_FLAGS;
````


## -struct-fields

### -field Enabled

Indicates whether the overlay plane is enabled for display.


### -field FlipImmediate

Indicates that the driver should perform a flip operation that occurs without vertical sync.


### -field FlipOnNextVSync

Indicates that the driver should perform a flip operation that occurs on the next vertical sync.

If the current line being displayed is less than DXGK_MULTIPLANE_OVERLAY_PLANE3.MaxImmediateFlipLine, the driver should convert this flip to an immediate flip and set DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS. FlipConvertedToImmediate to TRUE.


### -field SharedPrimaryTransition

Specifies that the driver is transitioning to or from a shared managed primary allocation.

This member is set if either of the following transitions occurs:


<ul>
<li>The current primary allocation is not a shared primary allocation, but the new one is.</li>
<li>The current primary allocation is a shared primary allocation, but the new one is not.</li>
</ul>
When SharedPrimaryTransition is set, the display miniport driver must validate that the hardware can seamlessly switch back and forth between primary and shared primary allocations, and it must perform any hardware programming needed to make the seamless switch occur.


### -field IndependentFlipExclusive

When IndependentFlipExlusive is set, the flip is done in the independent flip exclusive mode. The front buffer is accessed only by the display hardware and not by the DWM. The kernel mode driver can apply vertical sync-related optimizations. 


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 27 bits (0xFFFFFFE0) of the 32-bit <b>Value</b> member to zeros.


### -field Value


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>