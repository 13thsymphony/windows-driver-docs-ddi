---
UID: NS:d3dkmddi._DXGK_SET_TIMING_FLAGS
title: _DXGK_SET_TIMING_FLAGS
author: windows-driver-content
description: Structure to hold flags used to modify SetTiming behavior. Currently no flags are defined.
old-location: display\dxgk_set_timing_flags.htm
old-project: display
ms.assetid: BB10EBD3-2CB6-4854-994D-B10929CB27FC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_SET_TIMING_FLAGS, DXGK_SET_TIMING_FLAGS
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
req.alt-api: DXGK_SET_TIMING_FLAGS
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
req.typenames: DXGK_SET_TIMING_FLAGS
---

# _DXGK_SET_TIMING_FLAGS structure



## -description
Structure to hold flags used to modify SetTiming behavior.  Currently no flags are defined.



## -syntax

````
typedef struct _DXGK_SET_TIMING_FLAGS {
  union {
    struct {
      UINT Reserved;
    };
    UINT Value;
  };
} DXGK_SET_TIMING_FLAGS, *PDXGK_SET_TIMING_FLAGS;
````


## -struct-fields

### -field Reserved

This value is reserved for system use.


### -field Value

UINT used to operate on the combined bit-fields.


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