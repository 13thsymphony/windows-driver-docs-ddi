---
UID: NS.D3DKMDDI._DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
title: _DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
author: windows-driver-content
description: A structure containing the flags used to set the VidPN source address.
old-location: display\dxgk_setvidpnsourceaddress_output_flags.htm
old-project: display
ms.assetid: CFEEB41D-050F-4372-AB54-39ABC696C89D
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS, DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
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
req.alt-api: DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
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

# _DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS structure



## -description
A structure containing the flags used to set the VidPN source address.



## -syntax

````
typedef struct _DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS {
  union {
    struct {
      UINT PrePresentNeeded  :1;
      UINT Reserved  :31;
    };
    UINT Value;
  };
} DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS;
````


## -struct-fields

### -field PrePresentNeeded

Indicates that the driver must be called again at the PASSIVE_LEVEL to perform the requested operation.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


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