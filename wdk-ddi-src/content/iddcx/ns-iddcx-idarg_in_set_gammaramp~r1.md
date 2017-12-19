---
UID: NS.IDDCX.IDARG_IN_SET_GAMMARAMP~R1
title: IDARG_IN_SET_GAMMARAMP
author: windows-driver-content
description: Gives information about the gamma ramp being set.
old-location: display\idarg_in_set_gammaramp.htm
old-project: display
ms.assetid: 1e14bcaf-1454-4930-a3b8-afc044c4be3f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IDARG_IN_SET_GAMMARAMP,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDARG_IN_SET_GAMMARAMP
req.alt-loc: iddcx.h
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

# IDARG_IN_SET_GAMMARAMP structure



## -description
Gives information about the gamma ramp being set.
             



## -syntax

````
typedef struct IDARG_IN_SET_GAMMARAMP {
  IDDCX_GAMMARAMP_TYPE                          Type;
  UINT                                          GammaRampSizeInBytes;
  _Field_size_bytes_opt_(DataSizeInBytes) PVOID pGammaRampData;
} IDARG_IN_SET_GAMMARAMP, *IDARG_IN_SET_GAMMARAMP;
````


## -struct-fields

### -field Type


                     [in] The type of gamma ramp being set.
                 


### -field GammaRampSizeInBytes


                     [in] Size in bytes of the provided gamma ramp data.  Set to zero for <a href="..\iddcx\ne-iddcx-iddcx_gammaramp_type.md">IDDCX_GAMMARAMP_TYPE</a>.


### -field pGammaRampData


                     [in] Pointer to gamma ramp data to set.  Set to NULL for <a href="..\iddcx\ne-iddcx-iddcx_gammaramp_type.md">IDDCX_GAMMARAMP_TYPE</a>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>