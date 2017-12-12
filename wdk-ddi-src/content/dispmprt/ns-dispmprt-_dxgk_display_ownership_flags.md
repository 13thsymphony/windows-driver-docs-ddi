---
UID: NS.DISPMPRT._DXGK_DISPLAY_OWNERSHIP_FLAGS
title: _DXGK_DISPLAY_OWNERSHIP_FLAGS
author: windows-driver-content
description: Structure filled in by OS upon successful completion of the DxgkCbAcquirePostDisplayOwnership2 callback to provide information about the display state a driver is inheriting.
old-location: display\dxgk_display_ownership_flags.htm
old-project: display
ms.assetid: F5CA04FD-5E2A-4C68-97CF-F3D425A958AA
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_DISPLAY_OWNERSHIP_FLAGS, DXGK_DISPLAY_OWNERSHIP_FLAGS, *PDXGK_DISPLAY_OWNERSHIP_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_DISPLAY_OWNERSHIP_FLAGS
req.alt-loc: dispmprt.h
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

# _DXGK_DISPLAY_OWNERSHIP_FLAGS structure



## -description
Structure filled in by OS upon successful completion of the DxgkCbAcquirePostDisplayOwnership2 callback to provide information about the display state a driver is inheriting.



## -syntax

````
typedef struct _DXGK_DISPLAY_OWNERSHIP_FLAGS {
  union {
    struct {
      DXGK_FRAMEBUFFER_STATE FrameBufferState  :4;
    };
    UINT Value;
  };
} DXGK_DISPLAY_OWNERSHIP_FLAGS, *PDXGK_DISPLAY_OWNERSHIP_FLAGS;
````


## -struct-fields

### -field FrameBufferState

Value indicating the state of the frame buffer.  See definition of DXGK_FRAMEBUFFER_STATE enum for details.  


### -field Value

The value used to operate over the combined bitfields.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dispmprt.h</dt>
</dl>
</td>
</tr>
</table>