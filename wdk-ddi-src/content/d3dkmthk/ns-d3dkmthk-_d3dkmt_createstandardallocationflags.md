---
UID: NS.D3DKMTHK._D3DKMT_CREATESTANDARDALLOCATIONFLAGS
title: _D3DKMT_CREATESTANDARDALLOCATIONFLAGS
author: windows-driver-content
description: Used to create standard allocation flags.
old-location: display\d3dkmt-createstandardallocationflags.htm
old-project: display
ms.assetid: a1a4aa0c-2edc-48b9-ad49-c876be930955
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMT_CREATESTANDARDALLOCATIONFLAGS, D3DKMT_CREATESTANDARDALLOCATIONFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_CREATESTANDARDALLOCATIONFLAGS
req.alt-loc: d3dkmthk.h
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
---

# _D3DKMT_CREATESTANDARDALLOCATIONFLAGS structure



## -description
Used to create standard allocation flags.



## -syntax

````
typedef struct _D3DKMT_CREATESTANDARDALLOCATIONFLAGS {
  union {
    struct {
      UINT Reserved  :32;
    };
    UINT Value;
  };
} D3DKMT_CREATESTANDARDALLOCATIONFLAGS;
````


## -struct-fields

### -field Reserved

This value is reserved for use by the operating system.


### -field Value

The value used to operate over the other members.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h</dt>
</dl>
</td>
</tr>
</table>